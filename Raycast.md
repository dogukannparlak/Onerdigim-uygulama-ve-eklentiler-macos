# 🛠️ Raycast

> **Kısa Açıklama:** Klavye odaklı genişletilebilir başlatıcı; uygulama açma, pano geçmişi, dosya arama, pencere yönetimi, snippet'ler ve binlerce eklentiyle macOS iş akışını tek merkezden yönetmeni sağlar.

v1.104.19 · macOS 13+ (Apple Silicon / Intel) · Freemium · Üretkenlik / başlatıcı

---

## 📌 Genel Bakış

**Raycast**, Spotlight ve Alfred tarzı başlatıcıların ötesine geçen, yerleşik araçlar ve topluluk eklentileriyle genişleyen bir üretkenlik platformudur. Uygulama açmaktan pano geçmişine, hesap makinesinden pencere yönetimine kadar birçok işi klavyeden yapmanı sağlar; [Extension Store](https://www.raycast.com/store) üzerinden Spotify, Homebrew, Google Translate, GitHub ve daha yüzlerce entegrasyon eklenebilir.

Temel özellikler **ücretsiz ve kalıcı** olarak kullanılabilir; ancak Raycast tamamen ücretsiz bir uygulama değildir. **Raycast Pro** aboneliği yapay zeka, sınırsız pano geçmişi, bulut senkronizasyonu, sınırsız notlar ve özel temalar gibi gelişmiş özellikleri açar. Ücretsiz planda pano geçmişi **3 ay**, Raycast Notes **5 not** ile sınırlıdır. Ayrıntılı plan karşılaştırması aşağıdaki bölümde ve [resmi fiyatlandırma sayfasında](https://www.raycast.com/pricing) yer alır.

Windows (beta) ve iOS sürümleri de mevcuttur; aynı hesapla platformlar arası Pro avantajları paylaşılır. İlk keşfedildiğinde yalnızca Mac'teydi; günümüzde Windows beta ve iOS da var, ancak en olgun deneyim hâlâ macOS'tadır.

> 📺 Bu rehberdeki birçok kullanım örneği **Yusuf İpekin**'in [Raycast inceleme videosundan](https://www.youtube.com/watch?v=t9MxhQyuipw&t=11s) esinlenmiştir; fiyatlandırma ve limit bilgileri resmi kaynaklara göre güncellenmiştir.

---

## 💳 Ücretsiz vs Pro

| Özellik | Ücretsiz | Pro |
| ------- | -------- | --- |
| Başlatıcı, dosya arama, hesap makinesi, emoji | ✓ | ✓ |
| Pano geçmişi, snippet, quicklink, pencere yönetimi | ✓ (temel) | ✓ |
| Extension Store ve geliştirici araçları | ✓ | ✓ |
| Pano geçmişi süresi | 3 ay | Sınırsız |
| Raycast Notes | 5 not | Sınırsız |
| Raycast AI | 50 mesaj deneme + BYOK / Ollama | Tam erişim |
| Bulut senkronizasyonu (Mac, iOS, Windows) | - | ✓ |
| Özel temalar, Translator | - | ✓ |
| Özel pencere yönetimi komutları | En fazla 5 | Sınırsız |

**Fiyatlandırma (bireysel Pro):** Aylık **$10/ay** veya yıllık faturalamada **$8/ay** (%20 indirim). Yeni kullanıcılar **14 gün ücretsiz deneme** alır. Doğrulanmış öğrenciler için Pro'da **%50 indirim** uygulanır. **Advanced AI** eklentisi Pro'ya ek olarak ayrı ücretlendirilir.

> Bu rehber hem ücretsiz planda kullanılabilen hem de Pro'ya özel özellikleri ayırarak anlatır. "Tamamen ücretsiz" ifadesi yanıltıcıdır; günlük kullanım için ücretsiz plan geniş olsa da AI, sınırsız pano, bulut senkronizasyonu ve sınırsız notlar Pro gerektirir.

---

## ✨ Öne Çıkan Özellikler

### Ücretsiz planda (temel)

- **Uygulama ve komut başlatıcı** - Klavyeden uygulama, sistem komutu ve eklenti arama
- **Pano geçmişi (Clipboard History)** - Metin, resim, dosya, link ve renk filtreleme; son **3 ay** saklanır
- **Dosya arama (File Search)** - Sistem genelinde hızlı dosya arama; alias atanabilir (ör. `fs`)
- **Pencere yönetimi (Window Management)** - Yarım ekran, çeyrek, monitörler arası taşıma; kısayol atanabilir
- **Snippet'ler** - Anahtar kelimeyle metin genişletme (adres, imza, telefon vb.)
- **Quicklinks** - Sık sitelerde hızlı arama (`yt`, `ddg` gibi alias'larla)
- **Hesap makinesi ve kur** - Matematik, döviz çevrimi; hesap geçmişi
- **Takvim (My Schedule)** - Günün etkinliklerini listeleme
- **Emoji seçici** - Yazarken hızlı emoji ekleme
- **Renk seçici (Color Picker)** - Ekrandan renk alıp HEX/RGB kopyalama
- **Extension Store** - Binlerce topluluk eklentisi (Homebrew, OCR, çeviri, GitHub vb.)
- **Script Commands** - Shell, Python ve benzeri betikleri komut olarak çalıştırma
- **Raycast Notes** - Hızlı not alma (**en fazla 5 not**)
- **Menü çubuğunu gizleme (Toggle Menu Bar)** - Kısayolla üst menü çubuğunu saklama
- **Yazma pratiği (Start Typing Practice)** - Klavye hız pratiği

### Pro ile eklenenler

- **Raycast AI** - Entegre yapay zeka sohbeti ve komutları
- **Sınırsız pano geçmişi** - Ayarlardan "unlimited" seçilebilir
- **Bulut senkronizasyonu** - Snippet, quicklink, ayar ve notları cihazlar arası eşitleme
- **Sınırsız Raycast Notes** - Markdown destekli notlar
- **Translator** - Gelişmiş çeviri akışları
- **Özel temalar** - Arayüz kişiselleştirme
- **Sınırsız özel pencere yönetimi komutları**
- **Gelişmiş hesap makinesi (Advanced Calculator)** - Spotlight'ın ötesinde ek hesap akışları

---

## 📥 İndirme ve Kurulum

### Yöntem 1: Homebrew (Önerilen)

```bash
brew install --cask raycast
```

Güncelleme:

```bash
brew update
brew upgrade --cask raycast
```

> Homebrew yüklü değilse: [brew.sh](https://brew.sh) adresindeki komutu Terminal'de çalıştır.

### Yöntem 2: Resmi İndirme

1. [raycast.com](https://www.raycast.com/) adresine git
2. **Download for Mac** ile en güncel sürümü indir
3. `Raycast.app` dosyasını **Applications** klasörüne sürükle
4. Gatekeeper uyarısı çıkarsa: Sistem Ayarları → Gizlilik ve Güvenlik → Yine de Aç

> Windows beta ve iOS sürümleri için aynı sitedeki ilgili indirme bağlantılarını kullan.

---

## ⚙️ İlk Kurulum ve Önerilen Ayarlar

1. **Başlatıcı kısayolu:** Varsayılan `Option + Space` - **Raycast Settings → General → Hotkey** bölümünden Spotlight ile çakışmayacak şekilde ayarla
2. **Girişte başlat:** **Settings → General → Launch at login** - arka planda sürekli çalışması için
3. **Erişilebilirlik izni:** Pencere yönetimi ve bazı eklentiler için Sistem Ayarları → Gizlilik ve Güvenlik → **Erişilebilirlik** → Raycast'i etkinleştir
4. **Pano geçmişi gizliliği:** Veriler varsayılan olarak yerelde kalır; hesap açmadan kullanılabilir. Bulut senkronizasyonu yalnızca Pro + hesap ile devreye girer
5. **Extension alias'ları:** **Settings → Extensions** → sık kullandığın komutlara kısa alias ata (ör. File Search → `fs`, Clipboard History → `clip`)
6. **Pro kullanıyorsan pano süresi:** **Settings → Clipboard History → Keep history for…** → **Unlimited** (Pro'da manuel seçim gerekir)
7. **Hesap (isteğe bağlı):** Pro denemesi, bulut senkronizasyonu veya cihazlar arası ayar için [raycast.com](https://www.raycast.com/) üzerinden hesap oluştur

> 💡 Spotlight'ı tamamen kapatmak zorunda değilsin; Raycast'i farklı bir kısayola atayıp ikisini birlikte kullanabilirsin. Pencere yönetimi için ayrıca [Rectangle](Rectangle.md) kuruluysa kısayol çakışmalarını kontrol et.

---

## 🚀 Temel Kullanım

### Komut alias ve kısayol atama

Videoda vurgulandığı gibi neredeyse her yerleşik komut ve eklenti özelleştirilebilir:

1. **Settings → Extensions** → ilgili eklentiyi seç
2. **Alias** alanına kısa tetikleyici yaz - örneğin File Search → `fs`, Clipboard History → `clip`
3. **Hotkey** alanına global kısayol ata - pencere yönetimi ve Quick Translate gibi sık eylemler için
4. Raycast açıkken bu kısayollar arka planda doğrudan çalışır; başlatıcıyı açmana gerek kalmaz

### Başlatıcıyı açma ve uygulama arama

1. `Option + Space` (veya atadığın kısayol) ile Raycast'i aç
2. Uygulama adını yaz - örneğin `Obsidian` → Enter ile başlat
3. Ok tuşları veya `Tab` ile alternatif eylemlere geç

### Pano geçmişi

1. `clip` veya **Clipboard History** komutunu aç
2. Arama kutusuna anahtar kelime yaz - örneğin daha önce kopyaladığın bir kelimeyle geçmişi süz
3. Filtreler: yalnızca metin, resim, dosya, link veya **renk** (HEX / RGB; tasarımcılar için)
4. Seçili öğeyi Enter ile yapıştır; Actions menüsünden tek kaydı sil veya tüm geçmişi temizle

Veriler varsayılan olarak **yalnızca yerelde** tutulur; Raycast hesabı açmadan kullanılabilir. Hesap + Pro ile bulut senkronizasyonu isteğe bağlıdır.

> Ücretsiz planda geçmiş **3 ay** ile sınırlıdır (videoda “son bir hafta” gibi hissettiren yoğun kullanımda yüzlerce kayıt birikebilir). Hassas veriler için ara ara temizle veya [Maccy](Maccy.md) gibi yalnızca yerel bir pano aracıyla birlikte değerlendir.

### Dosya arama

1. **File Search** komutunu aç (alias: `fs`)
2. Dosya adı veya uzantı yaz - örneğin `screenshot`, `.pdf`
3. Kapsam: yalnızca kullanıcı klasörü veya tüm Mac

### Pencere yönetimi

1. **Window Management** komutlarını aç - örneğin `Left Half`, `Right Half`, `Bottom Half`, `First Third`, `Second Fourth`, `Maximize`
2. **Settings → Extensions → Window Management** altından her komuta kısayol ata - yazarak aramak zorunda değilsin
3. Aktif pencereyi klavyeden konumlandır; çoklu monitörde **Next Display** / **Previous Display**, Space geçişi için **Next Desktop** kullan
4. Raycast arka planda açıkken atanan global kısayollar doğrudan çalışır

[Rectangle](Rectangle.md) gibi ayrı bir pencere yöneticisi kullanıyorsan işlev örtüşür; tek araca toplamak mümkündür.

### Snippet oluşturma

1. **Create Snippet** veya **Search Snippets** komutunu aç
2. Anahtar kelime tanımla - örneğin `!adres`
3. Genişletilecek metni gir ve kaydet
4. Herhangi bir metin alanında `!adres` yazınca otomatik tamamlanır

### Hesap makinesi ve kur

1. Raycast'i aç ve doğrudan ifade yaz - örneğin `24 * 70` veya `468 USD`
2. Anlık sonuç görünür; Enter ile panoya kopyala veya devam et
3. **Calculator History** komutuyla gün içinde yaptığın hesapları ve kur dönüşümlerini tarihli olarak geri çağır

Spotlight da basit hesap yapar; Raycast'in farkı **geçmiş tutması**dır. Gelişmiş hesap akışları Pro kapsamındadır.

### Takvim (My Schedule)

1. **My Schedule** komutunu aç
2. Bugünkü etkinlikler listelenir
3. Bir etkinliğe Enter bas → macOS **Takvim** uygulamasında detay açılır

### Emoji seçici

1. Metin yazarken Raycast emoji komutunu aç
2. Emoji seç → imleç konumuna otomatik eklenir
3. Actions menüsünden **Copy to Clipboard** ile panoya da alabilirsin

### Quicklink oluşturma

1. **Create Quicklink** veya **Search Quicklinks** komutunu aç
2. Ad ve URL şablonu gir - arama sorgusu için `{argument}` kullan
   Örnek: `https://kagi.com/search?q={argument}`
3. Hangi tarayıcıda / uygulamada açılacağını seç
4. Alias ata - örneğin `kg`, `yt`, `ddg`, `alt`
5. Raycast'te `kg merhaba` yaz → Enter ile tarayıcıda arama açılır

**Sık kullanılan quicklink örnekleri:**

| Alias | Hedef | URL şablonu (örnek) |
| ----- | ----- | ------------------- |
| `ddg` | DuckDuckGo arama | `https://duckduckgo.com/?q={argument}` |
| `yt` | YouTube arama | `https://www.youtube.com/results?search_query={argument}` |
| `alt` | AlternativeTo arama | `https://alternativeto.net/browse/search/?q={argument}` |
| `kg` | Kagi arama | `https://kagi.com/search?q={argument}` |

> `{argument}` unutulursa quicklink çalışmaz - sorgu yerine boşluk bırakıp placeholder'ı URL'ye ekle.

### Eklenti kurma ve yönetme

1. Raycast'te **Store** yaz veya [raycast.com/store](https://www.raycast.com/store) adresine git
2. **Featured**, **Trending** veya arama ile keşfet → **Install Extension**
3. **Settings → Extensions** altından alias, kısayol ve tercihleri yapılandır
4. Her eklentinin desteklediği komutları aynı menüden gör; istemediğin eklentiyi **Uninstall** ile kaldır
5. Web geliştirme bilgin varsa kendi eklentini yazıp Store'a gönderebilirsin - [Developer Docs](https://developers.raycast.com/)

> Eklentilerin büyük çoğunluğu **yerelde** çalışır. AI özetleme, çeviri veya harici API kullanan eklentiler buluta veri gönderebilir; kurmadan önce açıklamayı oku.

### Google Translate (Quick Translate)

1. Store'dan **Google Translate** eklentisini kur
2. Kaynak dili otomatik algıla, hedef dili sabitle (ör. her zaman Türkçe)
3. **Quick Translate** komutuna global kısayol ata
4. Tarayıcıda veya herhangi bir uygulamada metni kopyala → kısayola bas → çeviri kenar panelde görünür; dili panelden değiştirebilirsin

### Homebrew eklentisi

Raycast üzerinden [Homebrew](Homebrew.md) paketlerini Terminal'e girmeden yönet:

- Paket ara ve kur - örneğin `inkscape`, `libreoffice`
- **brew upgrade** ile tüm paketleri güncelle
- **brew cleanup** ile artık dosyaları temizle
- Kurulu paketleri aynı arayüzden kaldır

### Easy OCR (ekran / görsel metin)

1. Store'dan **Easy OCR** kur; Tesseract dil paketinde **Türkçe**'yi etkinleştir
2. Kopyalanamayan metin içeren görseli panoya al veya ekranda seç
3. OCR komutunu çalıştır → metin panoya kopyalanır; Türkçe ve İngilizce metinlerde işe yarar

### CheckSum (dosya bütünlüğü)

1. **Get File Hash** ile dosya seç → SHA-256 (veya başka algoritma) hash'ini panoya al
2. **Verify File Hash** ile aynı dosyayı seçip hash'i yapıştır → eşleşme kontrolü
3. İsteğe bağlı: hash'i menü çubuğunda göster

### Renk seçici (Color Picker)

Varsayılan eklenti; global kısayol ata → ekrandan renk seç → HEX / RGB otomatik panoya kopyalanır.

### Raycast Notes

1. **Create Note** veya **Search Notes** komutunu kullan
2. Markdown desteklenir - `#` başlık, `-` madde işaretleri çalışır
3. Ücretsiz planda **en fazla 5 not**; limit aşıldığında Pro veya eski notları silme gerekir

### Menü çubuğunu gizleme

**Toggle Menu Bar** komutuna kısayol ata → odaklanırken üst menü çubuğunu anında gizle / göster.

### Klavye kısayolları (varsayılan ve örnekler)

| Kısayol | İşlev |
| ------- | ----- |
| `Option + Space` | Raycast'i aç (varsayılan; değiştirilebilir) |
| `Enter` | Seçili öğeyi çalıştır / yapıştır |
| `Cmd + K` | Actions menüsü |
| `Cmd + ,` | Raycast ayarları |
| `Esc` | Kapat / geri |

Komut ve eklenti kısayolları **Settings → Extensions** altında her öğe için ayrı atanır.

---

## 🔌 Store'dan Öne Çıkan Eklentiler

Videoda ve topluluk önerilerinde sık geçen eklentiler - tamamı Store'da aranabilir:

### Üretkenlik ve geliştirici

| Eklenti | Ne işe yarar |
| ------- | ------------ |
| **Homebrew** | Paket kur, güncelle, temizle |
| **GitHub** | Issue, pull request, workflow yönetimi |
| **Visual Studio Code** | Proje ve komut entegrasyonu |
| **Obsidian** | Not arama ve kontrol |
| **Apple Notes** | Notlara hızlı erişim |
| **Notion** | Sayfa arama ve oluşturma |
| **Linear / Slack** | Görev ve mesaj yönetimi |
| **1Password** | Vault'tan parola / kimlik bilgisi |
| **Docker** | Konteyner yönetimi (Docker yüklüyse) |
| **Vim Bro** | Unutulan Vim komutlarını arama |

### Tarayıcı ve medya

| Eklenti | Ne işe yarar |
| ------- | ------------ |
| **Google Chrome / Arc / Zen Browser** | Sekme, yer imi, geçmiş arama |
| **Spotify / YouTube Music** | Çalma kontrolü ve arama |
| **CleanShot X** | Ekran görüntüsü tetikleme |
| **Speed Test** | Dahili hız testi; görüntülü arama / streaming kalitesi göstergesi |

### Çeviri, AI ve metin

| Eklenti | Ne işe yarar |
| ------- | ------------ |
| **Google Translate** | Metin çevir; Quick Translate kısayolu |
| **ChatGPT** | Sohbet arayüzü - **API anahtarı gerekir** |
| **Perplexity / Google Gemini** | AI arama ve yanıt |
| **Apple Intelligence** | macOS'ta yüklüyse Apple Intelligence entegrasyonu |
| **Summarize YouTube Video** | Video özeti - **bulut / harici AI** kullanır |

### Tasarım, görsel ve dosya

| Eklenti | Ne işe yarar |
| ------- | ------------ |
| **Easy OCR / Screen OCR** | Görselden metin çıkarma |
| **SVGL** | Marka logolarını SVG olarak arama |
| **TinyPNG** | PNG sıkıştırma |
| **Remove Background** | Arka plan kaldırma |
| **Image Modification** | Temel görsel düzenleme |
| **CheckSum** | Dosya hash hesaplama ve doğrulama |
| **Color Picker** | Ekrandan renk alma (varsayılan) |

### Araçlar ve eğlence

| Eklenti | Ne işe yarar |
| ------- | ------------ |
| **URL Shortener** | Uzun linki kısalt |
| **Time Zone Converter** | Saat dilimi dönüşümü |
| **WhatsApp** | Sohbetlere hızlı erişim |
| **Reddit Search** | Reddit'te arama |
| **Meme Generator** | Metinlerden meme üretimi |
| **Convert** | Tarih, 3D model, web, müzik linki dönüştürme |
| **Start Typing Practice** | Klavye hız pratiği |

> ⚠️ **Video indirme** gibi telif ve platform kurallarına takılabilecek eklentiler Store'da görünse bile dikkatli kullan; YouTube içerikleri özellikle riskli olabilir.

---

## ⚠️ Bilinen Sorunlar ve Çözümleri

| Sorun | Neden Olur | Çözüm |
| ----- | ---------- | ----- |
| Pencere yönetimi çalışmıyor | Erişilebilirlik izni yok | Sistem Ayarları → Erişilebilirlik → Raycast'i etkinleştir; yeniden başlat |
| Spotlight ile çakışma | Aynı kısayol | Raycast veya Spotlight kısayolunu değiştir |
| Pro'da sınırsız pano yok | Varsayılan 3 ay limiti | Pro hesabıyla giriş yap → **Settings → Clipboard History → Unlimited** |
| Not oluşturulamıyor | Ücretsiz 5 not limiti | Eski notları sil veya Pro'ya geç |
| Eklenti kısayolu tepki vermiyor | Çakışan global kısayol | **Settings → Extensions** → ilgili eklentinin kısayolunu değiştir |
| Rectangle / AltTab ile çakışma | Aynı pencere kısayolları | Bir aracın kısayollarını devre dışı bırak veya farklı kombinasyon ata |
| Quicklink `{argument}` çalışmıyor | URL'de boşluk veya yanlış placeholder | `{argument}` ifadesini doğru konuma koy; kaydetmeden önce test et |

---

## 🔗 Faydalı Bağlantılar

- 🌐 [Resmi Web Sitesi](https://www.raycast.com/)
- 💳 [Fiyatlandırma (Free / Pro / Teams)](https://www.raycast.com/pricing)
- 🛒 [Extension Store](https://www.raycast.com/store)
- 📖 [Raycast Manual](https://manual.raycast.com/)
- 💰 [Faturalandırma ve planlar](https://manual.raycast.com/billing)
- 👨‍💻 [Geliştirici API](https://developers.raycast.com/)
- 🗣️ [Slack Topluluğu](https://raycast.com/community)
- 📦 [Homebrew Cask](https://formulae.brew.sh/cask/raycast)
- 📺 [Yusuf İpekin - Raycast inceleme videosu](https://www.youtube.com/watch?v=t9MxhQyuipw&t=11s)

---

## 📝 Notlar

> Raycast, Mac'te klavye odaklı çalışanlar için tek başına bir "mini işletim sistemi" gibi hissettiren en güçlü başlatıcılardan biridir. Ücretsiz plan günlük kullanım için oldukça geniştir; ancak yapay zeka, sınırsız pano, bulut senkronizasyonu ve sınırsız not isteyenler **Pro aboneliğine** ihtiyaç duyar. Pencere yönetimi ve pano için [Rectangle](Rectangle.md) ve [Maccy](Maccy.md) ile işlev örtüşmesi vardır - tek araca toplamak veya uzman araçlarla birlikte kullanmak kişisel tercihe bağlıdır. Windows'taki PowerToys veya Linux'taki KRunner/Ulauncher benzeri parçalı alternatifler vardır; Extension Store ekosistemi ve yerleşik araçların tek çatıda toplanması Raycast'i farklı konuma taşır. Store'da yüzlerce eklenti olduğu için herkesin ihtiyacına uygun bir komut mutlaka çıkar - düzenli tekrarlanan küçük işler (OCR, hash doğrulama, site araması, paket kurulumu) dakika kazandırır.

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
