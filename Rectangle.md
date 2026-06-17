# 🛠️ Rectangle

> **Kısa Açıklama:** Klavye kısayolları ve ekran kenarına sürükleyerek pencere boyutlandırma ve taşıma sunan; Spectacle'ın halefi olan ücretsiz, açık kaynaklı pencere yönetim aracı.

v0.96 · macOS 10.15+ (Apple Silicon / Intel) · MIT / açık kaynak · Pencere yönetimi

---

## 📌 Genel Bakış

macOS yerleşik olarak Split View sunar ama hızlı klavye ile yarım ekran, çeyrek ekran veya monitörler arası taşıma gibi işlemler için pratik değildir. **Rectangle**, eski Spectacle kullanıcılarının büyük ölçüde aynı kısayollarla geçiş yapabileceği olgun bir pencere yöneticisidir: aktif pencereyi klavye ile konumlandırır, ekran kenarına sürükleyince snap alanlarına yapıştırır ve çoklu monitör desteği sunar.

Tamamen ücretsiz ve açık kaynaktır; menü çubuğunda hafif bir simgeyle arka planda çalışır. Daha gelişmiş snap, özel boyut/konum kısayolları ve Space geçişi isteyenler [Rectangle Pro](https://rectangleapp.com/pro) gibi ücretli sürüme bakabilir; fare hareketleriyle pencere kontrolü için aynı geliştiricinin [Multitouch](https://multitouch.app/) uygulaması da Rectangle mantığını kullanır. Bu rehber yalnızca ücretsiz **Rectangle** sürümünü kapsar.

---

## ✨ Öne Çıkan Özellikler

- **Klavye kısayolları** - Yarım ekran, çeyrek, üçte bir, dörtte bir, maximize, restore ve daha fazlası
- **Snap alanları** - Pencereyi ekran kenarına veya köşesine sürükleyerek boyutlandırma
- **Spectacle uyumluluğu** - İlk çalıştırmada Spectacle varsayılan kısayollarını seçebilirsin
- **Kısayol tekrarı** - Aynı kısayolu tekrarlayarak boyut döngüsü (ör. üçte birler arasında geçiş)
- **Çoklu monitör** - Sonraki / önceki ekrana taşıma; isteğe bağlı monitörler arası gezinme
- **Ekstra eylemler** - Yalnızca yüksekliği maximize et, neredeyse tam ekran, kenara taşı (boyut değiştirmeden)
- **Uygulama yok sayma** - Belirli uygulamada kısayolları geçici olarak devre dışı bırak
- **JSON yapılandırma** - Ayarları dışa / içe aktar; makineler arası paylaş
- **URL şeması** - `rectangle://execute-action` ile otomasyon ve betik entegrasyonu
- **Tamamen ücretsiz** - Açık kaynak ([MIT](https://github.com/rxhanson/Rectangle/blob/main/LICENSE)); telemetri yok

---

## 📥 İndirme ve Kurulum

### Yöntem 1: Homebrew (Önerilen)

```bash
brew install --cask rectangle
```

Güncelleme:

```bash
brew update
brew upgrade --cask rectangle
```

> Homebrew yüklü değilse: [brew.sh](https://brew.sh) adresindeki komutu Terminal'de çalıştır.

### Yöntem 2: Resmi İndirme

1. [rectangleapp.com](https://rectangleapp.com/) adresine git
2. **Download** ile en güncel `.dmg` dosyasını indir (alternatif: [GitHub Releases](https://github.com/rxhanson/Rectangle/releases/latest))
3. `Rectangle.app` dosyasını **Applications** klasörüne sürükle
4. Gatekeeper uyarısı çıkarsa: Sistem Ayarları → Gizlilik ve Güvenlik → Yine de Aç

> macOS 10.13–10.14 için son desteklenen sürüm [v0.73](https://github.com/rxhanson/Rectangle/releases/tag/v0.73)'tür.

---

## ⚙️ İlk Kurulum ve Önerilen Ayarlar

1. **Erişilebilirlik izni (zorunlu):** Rectangle pencere boyutlandırmak için bu izne ihtiyaç duyar → Sistem Ayarları → Gizlilik ve Güvenlik → **Erişilebilirlik** → Rectangle'ı etkinleştir
2. **İlk çalıştırma sihirbazı:** Spectacle alışkanlığın varsa Spectacle varsayılan kısayollarını seç; yoksa Rectangle varsayılanlarıyla devam et
3. **Girişte başlat:** Rectangle menüsünden veya Sistem Ayarları → Genel → Giriş Öğeleri ile oturum açılışında başlat
4. **Snap sürükleme:** **Preferences → General** → **Snap windows by dragging** - Windows/Linux alışkanlığı için açık bırak; Notification Center donması yaşarsan kapat (aşağıdaki Bilinen Sorunlar)
5. **Monitörler arası gezinme:** Çoklu ekran kullanıyorsan **Allow windows to traverse across displays on subsequent left or right executions** seçeneğini değerlendir
6. **Çakışan uygulamalar:** Xcode, Terminal veya oyun gibi aynı kısayolları kullanan uygulamalar için menüden **Ignore app** ile Rectangle kısayollarını o uygulamada devre dışı bırak

> 💡 İlk kurulumda kısayollar çalışmıyorsa izin listesinde Rectangle görünse bile TCC eşleşmesi bozulmuş olabilir - aşağıdaki "Bilinen Sorunlar" bölümündeki yeniden yetkilendirme adımlarını uygula.

---

## 🚀 Temel Kullanım

### Klavye ile pencere konumlandırma

1. Konumlandırmak istediğin pencereyi öne getir (tıkla veya `Cmd + Tab`)
2. Atanmış kısayolu kullan - örneğin sol yarım ekran, sağ yarım ekran veya maximize
3. Aynı kısayolu tekrarlayarak döngüsel boyut değişimlerini dene (ör. üçte birler)

### Snap alanları (sürükleyerek)

Pencere başlık çubuğundan tutup ekran kenarına sürükle; imleç kenara ulaştığında Rectangle'ın uygulayacağı alan gösterilir, bıraktığında pencere o konuma oturur.

| Snap alanı | Sonuç |
| ---------- | ----- |
| Sol veya sağ kenar | Sol / sağ yarım ekran |
| Üst kenar | Maximize |
| Köşeler | İlgili çeyrek |
| Sol/sağ kenar, köşenin hemen altı/üstü | Üst / alt yarım |
| Alt kenar: sol, orta veya sağ üçte bir | İlgili üçte bir |
| Alt sol/sağ üçte bir → alt ortaya sürükle | İlk veya son iki üçte bir |

Dikey (portrait) monitörlerde üçte birler ekran yönüne göre uyarlanır.

### Uygulamayı yok sayma

1. Kısayol çakışması olan uygulamayı öne getir
2. Menü çubuğundaki Rectangle simgesi → **Ignore app**
3. Kaldırmak için uygulamayı tekrar öne getirip menüden seçimi kaldır

### Özel kısayol ekleme

**Preferences → General** sekmesinin altındaki **…** düğmesinden **Extra Shortcuts** bölümüne ek boyut/konum tanımlayabilirsin.

### Klavye kısayolları (Spectacle varsayılanları)

İlk kurulumda Spectacle seçtiysen tipik kısayollar aşağıdadır; tümü **Preferences → Shortcuts** sekmesinden özelleştirilebilir.

| Kısayol | İşlev |
| ------- | ----- |
| `⌃⌥←` | Sol yarım |
| `⌃⌥→` | Sağ yarım |
| `⌃⌥↑` | Üst yarım |
| `⌃⌥↓` | Alt yarım |
| `⌃⌥↩` | Maximize |
| `⌃⌥C` | Ortala |
| `⌃⌥⌘→` / `⌃⌥⌘←` | Sonraki / önceki ekran |
| `⌃⌥,` / `⌃⌥.` | Küçült / büyüt |
| `⌃⌥⌫` | Önceki boyuta geri al (restore) |

> `⌃` = Control, `⌥` = Option (Alt), `⌘` = Command

### URL ile otomasyon (isteğe bağlı)

Terminal veya kısayol uygulamalarından pencere eylemi tetikleyebilirsin:

```bash
open -g "rectangle://execute-action?name=left-half"
```

Kullanılabilir eylem adları için [GitHub README](https://github.com/rxhanson/Rectangle#execute-an-action-by-url) bölümüne bak.

---

## ⚠️ Bilinen Sorunlar ve Çözümleri

| Sorun | Neden Olur | Çözüm |
| ----- | ---------- | ----- |
| Kısayollar çalışmıyor | Erişilebilirlik izni eksik veya TCC bozulmuş | Sistem Ayarları → Erişilebilirlik → Rectangle'ı kapat, listeden kaldır, yeniden ekle; gerekirse `tccutil reset All com.knollsoft.Rectangle` |
| Pencere beklenen boyuta oturmuyor | Başka pencere yöneticisi veya çakışan kısayol | Raycast, AltTab veya benzeri araçları kapat; menüden eylemi dene; kısayolu değiştir |
| iTerm2 boyutu hafif kayık | Karakter genişliği snap'i | `defaults write com.googlecode.iterm2 DisableWindowSizeSnap -integer 1` |
| Notification Center donuyor | Snap sürükleme (nadir) | **Snap windows by dragging** seçeneğini kapat - [issue #317](https://github.com/rxhanson/Rectangle/issues/317) |
| Space / masaüstü geçişi yok | Apple public API sunmuyor | Ücretsiz Rectangle'ta yok; Space eylemleri yalnızca Rectangle Pro'da |
| Homebrew kurulumunda ayar kayboluyor | Eski plist kalıntısı | `brew uninstall --zap rectangle` ardından `brew install --cask rectangle` |
| macOS güncellemesi sonrası bozulma | TCC veya sistem servisleri | Mac'i kilitle/aç, yeniden başlat; izinleri sıfırla |

### Sorun giderme adımları

1. Mac'i kilitle/aç veya yeniden başlat (özellikle macOS güncellemesi sonrası)
2. Başka pencere yöneticisi çalışmadığından emin ol
3. Menü çubuğu simgesini açık tutarken **Option** basılı → **View Logging...** ile debug loglarını incele
4. Kalıcı sorunda yeni macOS kullanıcısı oluşturup test et; logları [GitHub Issues](https://github.com/rxhanson/Rectangle/issues)'a ekle

---

## 🔗 Faydalı Bağlantılar

- 🌐 [Resmi Web Sitesi](https://rectangleapp.com/)
- 💾 [GitHub Sayfası](https://github.com/rxhanson/Rectangle)
- 📦 [GitHub Releases](https://github.com/rxhanson/Rectangle/releases/latest)
- 📖 [Terminal gizli tercihleri](https://github.com/rxhanson/Rectangle/blob/main/TerminalCommands.md)
- 📖 [Spectacle farkları](https://github.com/rxhanson/Rectangle#differences-with-spectacle)
- 🗣️ [GitHub Discussions](https://github.com/rxhanson/Rectangle/discussions)
- 📦 [Homebrew Cask](https://formulae.brew.sh/cask/rectangle)
- 💎 [Rectangle Pro](https://rectangleapp.com/pro) · [Multitouch](https://multitouch.app/)

---

## 📝 Notlar

> Rectangle, Mac'te pencere düzenini klavye ve fareyle hızlı yönetmek isteyenler için en olgun ücretsiz seçeneklerden biridir. Spectacle'dan geçiş neredeyse sorunsuzdur; Dock önizlemesi veya uygulama geçişi arayanlar [DockDoor](DockDoor.md) veya [AltTab](AltTab.md) ile birlikte kullanabilir. Yapılandırma `~/Library/Preferences/com.knollsoft.Rectangle.plist` ve JSON dışa aktarımı ile yedeklenebilir; v0.44+ sürümlerde Preferences penceresinden import/export düğmeleri mevcuttur.

---

## ⚠️ Sorumluluk Reddi

Bu repository yalnızca bilgilendirme amaçlıdır. Burada önerilen uygulamalar ve eklentiler:

- **Kendi sorumluluğunuzda kullanın**: Uygulamaların sisteminizde neden olabileceği herhangi bir sorun, veri kaybı veya sistem hasarından sorumlu değiliz
- **Resmi kaynaklardan indirin**: Mutlaka uygulamaları resmi web sitelerinden veya güvenilir kaynaklardan indirin
- **Güncellik garantisi yoktur**: Uygulama bilgileri zaman içinde güncelliğini yitirebilir
- **Virüs/malware kontrolü yapın**: İndirdiğiniz dosyaları güvenlik yazılımınızla tarayın
- **Sistem yedeklemesi alın**: Önemli verilerinizi yedeklemeden yeni yazılım kurmayın
- **Lisans koşullarına dikkat edin**: Her uygulamanın kendi lisans koşulları vardır
- **Kişisel veri güvenliği**: Uygulamaların gizlilik politikalarını inceleyin

**Kullanım öncesi mutlaka araştırma yapın ve bu uygulamaları kendi riskinizle kullanın.**

---

*Son güncelleme: 2026-06-18*
