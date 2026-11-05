# İstop
Mobil tarayıcı için renk ve refleks oyunu. Mevcut sürüm HTML, CSS ve JavaScript'i tek bir Canvas 2D sayfasında içerir.

## Durum
5 Kasım 2026: mevcut oyun incelendi; modülerleşme ve çevrimdışı çalışma planı hazırlandı. **Plan kullanıcı onayı bekliyor; oyun kodu değiştirilmedi.** Aşağıdaki hedef mimari henüz uygulanmadı.

## Mevcut oyunu açma
Depo kökündeki index.html dosyasını tarayıcıda açabilirsiniz. Yerel HTTP testi için Python 3 varsa depo kökünde `python3 -m http.server 8000` çalıştırıp http://localhost:8000 adresini açın. Mevcut sürüm Google Fonts kullanır; çevrimdışı yeniden açılma garantisi henüz yoktur.

## Belgeler
- [Çalışma kuralları](AGENTS.md)
- [Proje bağlamı ve önerilen mimari](docs/PROJECT_CONTEXT.md)
- [Oyun tasarımı ve açık kararlar](docs/GAME_DESIGN.md)
- [Aşamalar ve kabul testleri](docs/ROADMAP.md)
- [Değişiklik geçmişi](docs/CHANGELOG.md)

## GitHub Pages hedefi
Onay sonrası main dalının kökünden statik yayın doğrulanacak. Derleme veya npm zorunluluğu planlanmıyor. Pages ayarları ve canlı yayın bu aşamada doğrulanmadı. Depo adı -stop iken beklenen yol /-stop/, istop olursa /istop/ olacaktır; ad değişikliği sonrası yollar ve çevrimdışı önbellek yeniden test edilmelidir.
