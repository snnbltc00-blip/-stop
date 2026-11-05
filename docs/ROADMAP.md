# Geliştirme aşamaları
Durum: Aşama 0 ve ayrıca onaylanan Bang Match temizliği tamamlandı. Aşama 1 için otomatik Klasik regresyon referansı oluşturuldu; kapsamlı cihaz kontrolleri sürüyor. Modülerleşme/çevrimdışı uygulama onay bekler.

| Aşama | Teslim | Bitiş ölçütü |
| --- | --- | --- |
| 0 — İnceleme ve plan | Mevcut kod envanteri, altı MD belge, açık kararlar | Belgeler ve kapsam kontrolü; kullanıcıya sunum |
| 1 — Davranış referansı | Mevcut oyunun tarayıcı kontrolü, kısa regresyon senaryoları | Çalışan akışlar ve mevcut sorunlar ayrı kaydedilmiş |
| 2 — Kademeli ayırma | CSS, kayıt/ses servisleri; ardından döngü, girdi, Klasik ve çizim | Her küçük taşımadan sonra aynı davranış; eski kayıtlar korunmuş |
| 3 — Mobil / çevrimdışı | Yerel varlıklar, service worker, mobil düzeltmeler | Soğuk çevrimdışı yeniden açılış ve sürüm geçişi başarılı |
| 4 — İlk prototip doğrulaması | GitHub Pages ve cihaz testi | Aşağıdaki kabul listesi geçti; sonuçlar belgelendi |
| 5 — Sonraki özellikler | Erişilebilirlik, Klasik içerik/denge | Ayrı kapsam ve kullanıcı önceliği belirlenmiş |

## Kabul ve regresyon listesi
- Açılış, menü, Klasik başlatma, doğru/yanlış top, süre dolması, tur geçişi, tekrar oynama.
- İstop hak tüketimi, dondurma süresi, puan ve rekorun başlangıç sürümüyle eşleşmesi.
- Duraklat/devam; uygulamayı arka plana alma ve geri dönüşte zaman sıçraması kontrolü.
- Ses/tema ayarları; sesin ilk kullanıcı etkileşimi sonrası çalışması.
- Eski kayıt göçü, bozuk JSON, eksik kayıt ve engelli localStorage durumunda çökmeden açılma.
- En az 360×640 ve 390×844 dikey ekran, yatay dönüş ve masaüstü fare; dokunma hedefleri, çentik ve taşma kontrolü.
- iOS Safari ve Android Chrome üzerinde temel oynanış; gerçek cihaz yoksa emülasyon sınırı raporlanır.
- Ön yükleme tamamlandıktan sonra ağ kapalıyken sekmeyi kapatıp yeniden açma; fontlar ve oyun çalışmalı.
- Yeni service worker sürümüne geçiş; yarım indirme, eski önbellek, kayıtların korunması.
- Pages proje alt yolunda tüm dosyalar 200; hatalı kök yolları ve konsol hataları yok.
- Koridor/Bang Match sistemleri çıkarılmış; Klasik özel toplar, ortak ses yardımcıları ve kayıt anahtarları korunmuş.

Saf kurallar ayrılınca zaman, skor, kayıt dönüşümü ve durum geçişlerine küçük bağımlılıksız testler eklenir. Canvas/pointer, ses, çevrimdışı ve görsel davranış tarayıcıda doğrulanır. Her aşamada yalnızca ilgili testler çalıştırılır.

## Bu aşamanın doğrulama sınırı
Chrome headless üzerinde tests/classic-regression.html ile 20 otomatik kontrol çalıştırıldı: kayıt göçü, giriş/menü, tur, skor, İstop, kayıp, tekrar oynama, duraklatma, tema/ses ayarları ve özel toplar. Aynı kontroller değişiklik öncesi sürümde de geçti; yeni sürüm 390×844, 360×640 ve 844×390 boyutlarında doğrulandı. Testler sabit rastgelelik ve elle ilerletilen zamanla oyun fonksiyonlarını gerçek Canvas ortamında çağırır; fiziksel dokunma, işitsel kalite veya uzun süreli oynanış testi değildir. Gerçek iOS/Android, çevrimdışı ve Pages yayın kontrolleri henüz yapılmadı.
