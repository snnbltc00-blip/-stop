# Proje bağlamı
Son güncelleme: 2026-11-05. Durum: koridor temizliği onaylandı ve tamamlandı; modülerleşme planı onay bekliyor.

## Kaynak ve mevcut durum
Yerel depo: -stop; GitHub: snnbltc00-blip/-stop; dal: main.
İncelenen başlangıç commit'i: fa1c247c66552452b2f4c5c3e4682341a5b3eb60.
Başlangıçta yalnızca README.md ve index.html mevcut. README güncellendi, eksik beş belge oluşturuldu.
index.html tek dosya arayüz, animasyon ve oyun kodunu içerir; CSS, Klasik oyun durumu, çizim, girdi ve kayıt içerir. Kullanıcı koridor modunun ayrı Bang Match projesine ait olduğunu belirtti; o modun kodu kaldırıldı. Paket veya derleme sistemi yoktur.

## Hızlı kod haritası
| Konu | index.html içindeki semboller |
| --- | --- |
| Ana menü ve giriş | menuLogo, menuUI2, updatePreview, finishVideoIntro, menuDown, startMode, down |
| Klasik oyun | newGame, wait, announce, win, lose |
| Güncelleme / çizim | upd, draw, loop, rs |
| Basılma / oyun sonu | buttonAt, beginButton, endButton, drawLose, lbt |
| Kayıt | S, sv2, saveProgress |
| Ses / tema | buttonClick, snd, dk, sheetTap, tr, settingsIcon |

Ana menü startMode üzerinden newGame çağırır. Koridor motoru, 100 seviye verisi, güçlendiriciler ve RENK EVRENİ alt başlıkları kaldırıldı. Ortak box/cheer ses yardımcıları ve Klasik özel topları korundu. Test kapsamı ROADMAP içinde kayıtlıdır.

Açılış varlığı: assets/baltx-intro.mp4. Menü önizlemesi oyuncu kaydından bağımsızdır. Arayüz ayrıntıları GAME_DESIGN ve CHANGELOG içindedir. Dil S.lang alanında mevcut tercih anahtarıyla saklanır.

## Korunacak veri
istop_classic_s, istop_classic_best, istop_classic_dk ve istop_classic_migrated anahtarları mevcut. Eski istop_s, istop_best ve istop_dk için taşıma kodu bulunur. Yeni veri şeması gerekirse sürümlü ve geriye uyumlu göç tasarlanır. Klasik kayıt tam oyun anı değil skor kaydıdır. Eski kayıtta bulunan diğer oyuna ait alanlar veri kaybını önlemek için pasif biçimde korunur; oyun bunları kullanmaz.

## Önerilen hedef mimari — henüz oluşturulmadı
```text
index.html                  # sayfa kabuğu, canvas, modül girişi
styles/main.css             # ekran, mobil ölçüler, tema temeli
src/main.js                 # başlangıç ve modülleri bağlama
src/core/loop.js             # zaman, güncelleme ve çizim çağrıları
src/core/state.js            # açık oyun durumu, geçişler
src/core/input.js            # pointer ve koordinat dönüşümü
src/game/classic.js          # klasik kurallar
src/render/canvas.js         # çizim ve ortak görsel yardımcılar
src/services/storage.js     # kayıt, doğrulama ve göç
src/services/audio.js       # ses ve titreşim
sw.js                       # çevrimdışı kabuk, sonraki aşamada
tests/classic-regression.html # mevcut bağımlılıksız tarayıcı testi
docs/
```
Bu yapı bir hedef haritadır; boş dosyalar önceden üretilmez. Önce CSS ve bağımsız servisler ayrılır; sıkı bağlı oyun/çizim durumu adım adım taşınır. Döngü girdi ve kuralları çalıştırır, çizim mevcut durumu okur; kayıt ve ses servisleri arayüzü yönetmez. ES modülleri göreli import kullanır, modül sürümü HTTP üzerinden test edilir. Genel event bus, ECS, framework veya TypeScript geçişi önerilmiyor.

## Çevrimdışı ve mobil yaklaşım
İlk başarılı çevrimiçi yükleme ve önbellek kurulumu sonrasında bağlantısız yeniden açılış hedeflenir; hiç indirilmemiş oyunun ilk açılışı kapsam dışıdır. Fontlar sistem fontuna çevrilir veya lisansı doğrulanarak yerelleştirilir; görsel kimlik tercihi onayda netleşir.
Service worker göreli kapsam, sürümlü önbellek ve yalnızca kendi eski önbelleklerini temizleme kullanmalıdır. Yarım güncelleme ve eski sürümden geçiş test edilir. PWA manifesti/kurulum deneyimi ayrı, isteğe bağlı aşamadır.
Mobilde dokunma, DPR, ekran dönüşü, çentik güvenli alanları ve arka plana geçiş test edilir. Renk dışı ipuçları ve erişilebilir menü kontrolleri sonraki iyileştirmedir.
