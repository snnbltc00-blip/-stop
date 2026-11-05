# İstop
Mobil tarayıcı için renk ve refleks oyunu. Mevcut sürüm HTML, CSS ve JavaScript'i tek bir Canvas 2D sayfasında içerir.

## Durum
5 Kasım 2026: mevcut oyun incelendi; modülerleşme ve çevrimdışı çalışma planı hazırlandı. **Kullanıcı talebiyle Bang Match/koridor kodu kaldırıldı; Klasik oyun korundu. Modülerleşme planı ayrıca onay bekliyor.** Aşağıdaki hedef mimari henüz uygulanmadı.

## Mevcut oyunu açma
Depo kökündeki index.html dosyasını tarayıcıda açabilirsiniz. Yerel HTTP testi için Python 3 varsa depo kökünde `python3 -m http.server 8000` çalıştırıp http://localhost:8000 adresini açın. Mevcut sürüm Google Fonts kullanır; çevrimdışı yeniden açılma garantisi henüz yoktur.

## Belgeler
- [Çalışma kuralları](AGENTS.md)
- [Proje bağlamı ve önerilen mimari](docs/PROJECT_CONTEXT.md)
- [Oyun tasarımı ve açık kararlar](docs/GAME_DESIGN.md)
- [Aşamalar ve kabul testleri](docs/ROADMAP.md)
- [Değişiklik geçmişi](docs/CHANGELOG.md)

## GitHub Pages
Mevcut oyun adresi korunur: [İstop'u aç](https://snnbltc00-blip.github.io/-stop/). Depo adı ve yayın yolu değiştirilmez.

## Güncel arayüz
3 saniyelik açılış videosu, canlı top animasyonlu tek modlu menü, TR/ENG, sessiz/koyu mod ve basılma efektleri bulunur. Video için `assets/baltx-intro.mp4` dosyası index.html yanında korunmalıdır. Ayrıntılar değişiklik geçmişindedir.

## Regresyon testi
Yerel HTTP sunucusunda [Klasik regresyon testini](tests/classic-regression.html) açın. Test, gerçek oyuncu kaydını kullanmadan ayrı iframe belleğinde 20 kontrol çalıştırır. `?width=360&height=640` parametreleriyle oyun ekranının boyutu değiştirilebilir.
