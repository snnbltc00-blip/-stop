# Oyun tasarımı
Durum: Klasik oyun korunarak Bang Match ayrıştırıldı; diğer öneriler onay bekliyor.

## Fikir değerlendirmesi
İstop, hareketli renkli toplar arasında hedef rengi yakalama ve zamanı kısa süreli durdurma üzerine kurulu tek oyunculu refleks oyunudur. Kısa oturum, tek elle dokunma ve anında geri bildirim mobil/çevrimdışı hedefe uygundur. Klasik sokak oyununun birebir uyarlaması olarak varsayılmamalıdır.
Başlıca riskler: dar ekranda yoğun toplar, yalnız renge dayalı ayırt etme, görsel efektlerin performansı ve ortak global durumun değişiklikleri kırması. Önce davranış korunmalı; denge ve yeni içerik daha sonra ele alınmalı.

## Kodda görülen kurallar
- Ana menüde “Oyuna Başla” düğmesi Klasik oyunu başlatır; arka plandaki otomatik oyun önizlemesi gerçek skoru etkilemez.
- Hedef renk duyurulur; oyuncu o renkteki topları süre dolmadan temizler.
- Klasik av süresi 5 saniye; yanlış top veya süre bitişi kaybettirir.
- Başlangıç İstop hakkı 3 + kayıtlı stok; kullanım 3 saniye dondurur.
- Tur ödülü isabet ve hız çarpanına bağlıdır; özel toplar, ilerleyen zorluk ve yeniden oynama akışı vardır.
- Kayıt, en iyi skor, ses ve koyu tema kodda mevcuttur.
- Bang Match projesine ait 100 seviyelik koridor sistemi ve güçlendiricileri kullanıcı talebiyle kaldırıldı. Klasik oyunun pembe, renk değiştiren, siyah ve beyaz topları korundu.

## Kritik kararlar
| Karar | Öneri | Durum |
| --- | --- | --- |
| Oyun kapsamı | Yalnız Klasik; Bang Match/koridor ayrı proje | Kullanıcı kararı uygulandı |
| Kurallar / zorluk | İlk geçişte süre, puan ve hakları aynen koru | Onay bekliyor |
| Çevrimdışı anlamı | İlk çevrimiçi yüklemeden sonra bağlantısız yeniden açılış | Onay bekliyor |
| Devam etme | Mevcut kayıt davranışını koru; tam tur anı kaydını ertele | Onay bekliyor |
| Ekran / cihaz | Dikey mobil öncelikli; yatayda oynanabilir yerleşim, masaüstü fare | Onay bekliyor |
| Görsel kimlik | Sade mor kutular, turkuaz eylemler, renkli toplar; ayrıntılar CHANGELOG | Arayüz güncellemeleri uygulandı |
| Hedef yaş / erişilebilirlik | Yaş grubu kullanıcıdan netleşmeli; renk dışı ipucu planlanmalı | Açık |
| Çevrimiçi özellikler | Hesap, çok oyunculu, reklam, ödeme ve sunucu ekleme | İlk kapsam dışında |

## İlk oynanabilir modüler prototip
Yeni bir oyun demosu değil, mevcut Klasik oyunun davranışı korunmuş modüler sürümüdür:
açılış → menü → oyun → kazanılan tur/kaybetme → tekrar oynama; İstop, puan, rekor, duraklatma, ses/tema ve mevcut özel top davranışları korunur. Koridor kodu kapsamdan çıkarıldı. Denge değişiklikleri bu teslimin parçası değildir.
İlk prototipin tamamlanması mobil temel testleri, kayıt uyumluluğu, çevrimdışı yeniden açılış ve GitHub Pages alt dizin testinin geçmesine bağlıdır. Yeni seviye, ekonomi veya tasarım yenilemesi eklenmez.

## Güncel arayüz
Açılış videosundan sonra tek modlu menü gelir. Dil yalnız ana menü ayarlarından değiştirilir. Her iki ayar kutusunda sessiz/koyu mod vardır; yeşil sessiz anahtarı sesi kapatır. İSTOP kutusu son duyurulan hedef rengini bir sonraki duyuruya kadar korur; pembe top bunu değiştirmez. Kayıp ekranında puan, rekor, tekrar oynama ve menüye dönüş bulunur. Butonlar basıldığında küçülür ve iç gölge alır.

Ana menü başlığı oyun içi İSTOP yazısıyla aynı font ailesini kullanır; açık temada mavi-mor, koyu temada açık lavanta mavisidir. Ses açıkken butona ilk basışta tek tok tıklama çalar; sessiz modda çalmaz.
