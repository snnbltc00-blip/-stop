# İstop — geliştirme kuralları

## Kapsam ve onay
Bu aşama yalnızca dokümantasyon ve planlamadır. Kullanıcı planı onaylamadan oyun kodunu, bağımlılıkları veya mimariyi değiştirme. GitHub'a belge yükleme talebi kod uygulama onayı sayılmaz.

## Az bağlamla güvenli çalışma
1. Önce git durumunu ve docs/PROJECT_CONTEXT.md dosyasını oku; ardından yalnızca görevle ilgili belgeyi ve kod bölümünü aç.
2. Dosya keşfi için rg --files, sembol bulmak için rg -n kullan. Büyük dosyaları baştan sona tekrar tekrar okuma; ilgili satır aralığını oku.
3. Tüm kodu yeniden üretme. Küçük, incelenebilir yamalarla yalnızca gerekli dosyaları değiştir.
4. Büyük işleri ayrı kabul ölçütleri olan aşamalara böl. Kullanıcı değişikliklerini koru.
5. Çalışan davranışları ve kayıt uyumluluğunu koru. Kullanılmıyor gibi görünen modları kanıt olmadan silme.
6. Yeni özellik için gereksiz katman, framework, paket, derleme sistemi veya genel amaçlı mimari ekleme.
7. Önemli değişiklikte yalnızca etkilenen MD belgelerini güncelle; CHANGELOG'a gerçek sonucu yaz, ROADMAP durumunu düzelt. Aynı ayrıntıyı bütün belgelere kopyalama.
8. Testleri atlama. Belge işinde bağlantı, kapsam ve diff; kod işinde değişen kurallar ve ilgili oyun akışı; kayıt işinde eski/bozuk/engelli depolama; çevrimdışı işinde soğuk açılış ve sürüm güncellemesini doğrula.
9. Çalıştırılamayan testi “geçti” diye yazma. Statik inceleme ile tarayıcı testini açıkça ayır.
10. Kısa rapor ver: değişenler, doğrulananlar, kalan engel veya karar. Uzun araç çıktıları ve tekrar eden planlardan kaçın.
11. Sırları, kimlik bilgilerini ve ilgisiz klasörleri okuma. Görev gerektirmedikçe tüm depo taraması yapma.
12. Sembol yerleri değişince bağlam belgesindeki dosya haritasını güncelle; kırılgan satır numaraları yerine sembol adları kullan.

## Teknik sınırlar
HTML, CSS, vanilla JavaScript ve mevcut Canvas 2D yaklaşımı esastır. Mobil dokunma ve fare desteklenir. Statik GitHub Pages alt dizininde göreli yollar kullanılmalıdır. Çevrimdışı oyun sunucuya veya CDN'e bağımlı olmamalıdır. Mevcut localStorage anahtarları uyumluluk planı olmadan değiştirilmez.
