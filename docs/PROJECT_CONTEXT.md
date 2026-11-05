# Proje bağlamı
Son güncelleme: 2026-11-05. Durum: plan onay bekliyor.

## Kaynak ve mevcut durum
Yerel depo: -stop; GitHub: snnbltc00-blip/-stop; dal: main.
İncelenen başlangıç commit'i: fa1c247c66552452b2f4c5c3e4682341a5b3eb60.
Başlangıçta yalnızca README.md ve index.html mevcut. README güncellendi, eksik beş belge oluşturuldu.
index.html yaklaşık 1028 satırdır; yoğun satırlar CSS, oyun durumu, çizim, girdi, kayıt ve iki modun kurallarını birleştirir. Paket veya derleme sistemi yoktur.

## Hızlı kod haritası
| Konu | index.html içindeki semboller |
| --- | --- |
| Ana menü ve giriş | MD, menuDown, startMode, down |
| Klasik oyun | newGame, wait, announce, win, lose |
| Güncelleme / çizim | upd, draw, loop, rs |
| Kayıt | S, sv2, saveProgress, resumeColor |
| Renk/koridor modu | LVC, LEVEL_NAMES, newSpiral, spDown, levelUp |
| Güçlendiriciler | BOOSTERS, useElectricBooster, useIceBooster, useVolcanoBooster |
| Ses / tema | snd, dk, sheetTap |

Ana menü startMode üzerinden newGame çağırır. Renk/koridor modu kodda vardır; normal menüden erişilebilir bir özellik olarak kabul edilmemelidir. Görsel ve oynanış sonuçları tarayıcıda henüz doğrulanmadı.

## Korunacak veri
istop_classic_s, istop_classic_best, istop_classic_dk ve istop_classic_migrated anahtarları mevcut. Eski istop_s, istop_best ve istop_dk için taşıma kodu bulunur. Yeni veri şeması gerekirse sürümlü ve geriye uyumlu göç tasarlanır. Klasik kayıt tam oyun anı değil skor kaydıdır; renk modu seviye ve skor saklar.

## Önerilen hedef mimari — henüz oluşturulmadı
```text
index.html                  # sayfa kabuğu, canvas, modül girişi
styles/main.css             # ekran, mobil ölçüler, tema temeli
src/main.js                 # başlangıç ve modülleri bağlama
src/core/loop.js             # zaman, güncelleme ve çizim çağrıları
src/core/state.js            # açık oyun durumu, geçişler
src/core/input.js            # pointer ve koordinat dönüşümü
src/game/classic.js          # klasik kurallar
src/game/color.js            # mevcut koridor modu, sonraki aşamada
src/game/levels.js           # mevcut seviye verileri, sonraki aşamada
src/render/canvas.js         # çizim ve ortak görsel yardımcılar
src/services/storage.js     # kayıt, doğrulama ve göç
src/services/audio.js       # ses ve titreşim
sw.js                       # çevrimdışı kabuk, sonraki aşamada
tests/                      # onay sonrası davranış testleri
docs/
```
Bu yapı bir hedef haritadır; boş dosyalar önceden üretilmez. Önce CSS ve bağımsız servisler ayrılır; sıkı bağlı oyun/çizim durumu adım adım taşınır. Döngü girdi ve kuralları çalıştırır, çizim mevcut durumu okur; kayıt ve ses servisleri arayüzü yönetmez. ES modülleri göreli import kullanır, modül sürümü HTTP üzerinden test edilir. Genel event bus, ECS, framework veya TypeScript geçişi önerilmiyor.

## Çevrimdışı ve mobil yaklaşım
İlk başarılı çevrimiçi yükleme ve önbellek kurulumu sonrasında bağlantısız yeniden açılış hedeflenir; hiç indirilmemiş oyunun ilk açılışı kapsam dışıdır. Fontlar sistem fontuna çevrilir veya lisansı doğrulanarak yerelleştirilir; görsel kimlik tercihi onayda netleşir.
Service worker göreli kapsam, sürümlü önbellek ve yalnızca kendi eski önbelleklerini temizleme kullanmalıdır. Yarım güncelleme ve eski sürümden geçiş test edilir. PWA manifesti/kurulum deneyimi ayrı, isteğe bağlı aşamadır.
Mobilde dokunma, DPR, ekran dönüşü, çentik güvenli alanları ve arka plana geçiş test edilir. Renk dışı ipuçları ve erişilebilir menü kontrolleri sonraki iyileştirmedir.
