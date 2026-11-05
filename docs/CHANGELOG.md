# Değişiklik geçmişi

## 2026-11-05 — Başlık ve buton sesi
- Ana menü başlığı oyun içindeki İSTOP butonuyla aynı yazı tipine (Caveat Brush ve mevcut yedek fontlar) geçirildi. Açık temada mavi-mor, koyu temada açık lavanta mavisi dolgu ve belirgin kontur kullanılır; dolgu tek tondur.
- Ses açıkken butona basıldığında kısa, tok tıklama sesi eklenir. Sessiz modda üretilmez; basılı tutma ve bırakma sesi tekrar tetiklemez.
- Kullanılmayan Coiny font isteği kaldırıldı; kayıt anahtarları ve oyun kuralları değişmedi.
- Chrome üzerinde font eşleşmesi, iki tema, gerçek AudioContext üretimi, sessiz mod ve fare/dokunma davranışı doğrulandı. Fiziksel cihazda sesin işitsel değerlendirmesi ayrıca yapılmalıdır.

## 2026-11-05 — Arayüz ve animasyon güncellemeleri
- Yerel 3 saniyelik BALTX videosu sessiz otomatik açılışa eklendi; bitince ana menü açılır.
- Tek modlu menü, rekor, küçük renk değiştiren başlat düğmesi ve bağımsız top animasyonu oluşturuldu. Her 3 saniyede hedef renk değişir; eş renkli toplar sırayla patlar, son topta tur patlama efekti çıkar.
- Ayarlar ve oyun sonu kutuları sade mor temaya uyarlandı; yuvarlak dişli simgeleri ve tüm butonlara basılma efekti eklendi.
- Yeşil/sağ sessiz anahtarı sesi kapatır, notayı çizer; koyu modda hilal yıldızları parlar.
- TR/ENG seçimi yalnız ana menüde bulunur, tüm oyun metinlerini çevirir; mevcut tercih kaydında lang alanı kullanılır.
- Skor beyaz yıldızla, tur simgesiz gösterilir. Kalan top yazısı kaldırıldı. İSTOP son duyurulan renkte kalır; pembe top rengi değiştirmez.
- Menü butonları bırakılınca çalışır; İSTOP anlık tepki verir. Sürükleme/iptal durumları ele alındı.
- Yerel Chrome tarayıcı testlerinde oyun akışı, dil, kayıt hataları, efekt izolasyonu, fare/dokunma ve ekran boyutları doğrulandı. Fiziksel iOS/Android ve çevrimdışı kullanım doğrulanmadı.

## 2026-11-05 — Bang Match kodunun ayrılması
- Kullanıcı onayıyla 100 seviyelik koridor motoru, seviye ekranları, elektrik/buz/volkan güçlendiricileri ve ilgili girdi/çizim dalları kaldırıldı.
- RENK EVRENİ alt başlıkları temizlendi; Klasik kurallar, özel toplar ve ortak ses yardımcıları korundu.
- Dosya yaklaşık 133 KB’den 44 KB’ye küçüldü; yeni bağımlılık eklenmedi.
- Eski kayıt anahtarları ve diğer oyuna ait mevcut kayıt verileri silinmedi.
- Bağımlılıksız 20 kontrollü tarayıcı regresyon testi eklendi; genel modülerleşme onayı hâlâ bekleniyor.

## 2026-11-05 — Planlama
- Mevcut README güncellendi; AGENTS.md ve docs altında PROJECT_CONTEXT, GAME_DESIGN, ROADMAP, CHANGELOG oluşturuldu.
- Token tasarrufu, dar kapsamlı değişiklik, kayıt uyumluluğu ve test kuralları belirlendi.
- Klasik akış ile kodda bulunan koridor/seviye sisteminin erişim farkı kaydedildi.
- Modüler mimari, çevrimdışı yaklaşım ve ilk prototip kabul ölçütleri önerildi.
- Plan uygulama onayı bekliyor. Oyun kodu, bağımlılıklar ve yayın ayarları değiştirilmedi.
