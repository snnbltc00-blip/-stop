# Oyun tasarımı
Durum: mevcut koddan çıkarılmış değerlendirme + onay bekleyen öneriler.

## Fikir değerlendirmesi
İstop, hareketli renkli toplar arasında hedef rengi yakalama ve zamanı kısa süreli durdurma üzerine kurulu tek oyunculu refleks oyunudur. Kısa oturum, tek elle dokunma ve anında geri bildirim mobil/çevrimdışı hedefe uygundur. Klasik sokak oyununun birebir uyarlaması olarak varsayılmamalıdır.
Başlıca riskler: dar ekranda yoğun toplar, yalnız renge dayalı ayırt etme, görsel efektlerin performansı ve ortak global durumun değişiklikleri kırması. Önce davranış korunmalı; denge ve yeni içerik daha sonra ele alınmalı.

## Kodda görülen kurallar
- Ana menüde “Renkleri Yakala” kartı Klasik oyunu başlatır.
- Hedef renk duyurulur; oyuncu o renkteki topları süre dolmadan temizler.
- Klasik av süresi 5 saniye; yanlış top veya süre bitişi kaybettirir.
- Başlangıç İstop hakkı 3 + kayıtlı stok; kullanım 3 saniye dondurur.
- Tur ödülü isabet ve hız çarpanına bağlıdır; özel toplar, ilerleyen zorluk ve yeniden oynama akışı vardır.
- Kayıt, en iyi skor, ses ve koyu tema kodda mevcuttur.
- Ayrı renk/koridor sisteminde 100 seviyelik yapı; elektrik (10 sn), buz (5 sn), volkan (seçilen rengi temizleme) güçlendiricileri bulunur. Bu kodun mevcut menüye eklenmesi yeni kapsamdır.

## Kritik kararlar
| Karar | Öneri | Durum |
| --- | --- | --- |
| İlk modüler sürümün odağı | Klasik; koridor kodunu koru, görünürlüğünü değiştirme | Onay bekliyor |
| Kurallar / zorluk | İlk geçişte süre, puan ve hakları aynen koru | Onay bekliyor |
| Çevrimdışı anlamı | İlk çevrimiçi yüklemeden sonra bağlantısız yeniden açılış | Onay bekliyor |
| Devam etme | Mevcut kayıt davranışını koru; tam tur anı kaydını ertele | Onay bekliyor |
| Ekran / cihaz | Dikey mobil öncelikli; yatayda oynanabilir yerleşim, masaüstü fare | Onay bekliyor |
| Görsel kimlik | Mevcut görünümü koru; fontu yerelleştirme tercih edilir | Onay bekliyor |
| Hedef yaş / erişilebilirlik | Yaş grubu kullanıcıdan netleşmeli; renk dışı ipucu planlanmalı | Açık |
| Çevrimiçi özellikler | Hesap, çok oyunculu, reklam, ödeme ve sunucu ekleme | İlk kapsam dışında |

## İlk oynanabilir modüler prototip
Yeni bir oyun demosu değil, mevcut Klasik oyunun davranışı korunmuş modüler sürümüdür:
açılış → menü → oyun → kazanılan tur/kaybetme → tekrar oynama; İstop, puan, rekor, duraklatma, ses/tema ve mevcut özel top davranışları korunur. Mevcut koridor kodu silinmez; menüye açılması ve denge değişiklikleri bu teslimin parçası değildir.
İlk prototipin tamamlanması mobil temel testleri, kayıt uyumluluğu, çevrimdışı yeniden açılış ve GitHub Pages alt dizin testinin geçmesine bağlıdır. Yeni seviye, ekonomi veya tasarım yenilemesi eklenmez.
