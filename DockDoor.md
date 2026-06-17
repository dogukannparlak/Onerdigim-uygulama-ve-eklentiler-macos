# 🛠️ DockDoor

> **Kısa Açıklama:** macOS'un yerleşik Dock'una canlı pencere önizlemeleri, Windows tarzı `Option + Tab` geçişi ve klavye/fare ile pencere kontrolleri ekleyen ücretsiz, açık kaynaklı bir pencere yönetim aracı.

v1.39.3 · macOS 13 Ventura+ (Apple Silicon / Intel) · GPL-3.0 / açık kaynak · Pencere yönetimi

---

## 📌 Genel Bakış

macOS Dock'unda bir uygulamanın üzerine gelince açık pencereleri göremezsin; hangi pencereye geçeceğini anlamak için tıklayıp `Cmd + \`` ile gezmen gerekir. Yerleşik `Cmd + Tab` ise yalnızca uygulama simgelerini gösterir, pencere önizlemesi sunmaz.

**DockDoor**, Windows ve Linux'taki "window peeking" deneyimini Mac'e getirir: Dock simgesinin üzerine gelince o uygulamanın tüm açık pencereleri canlı önizleme olarak çıkar; tıklamadan önce ne açacağını görürsün. Üstelik yerleşik Dock'u **değiştirmez**, üzerine özellik ekler. Tamamen ücretsiz, açık kaynak ve gizlilik odaklıdır - telemetri, analitik veya bulut bağlantısı yoktur.

> **DockDoor Pro** ayrı bir ücretli uygulamadır ([pro.dockdoor.net](https://pro.dockdoor.net/)); Dock'u tamamen değiştirir. Bu rehber yalnızca ücretsiz **DockDoor** sürümünü kapsar.

---

## ✨ Öne Çıkan Özellikler

*(Yalnızca ücretsiz sürüm özellikleri)*

- **Dock önizlemeleri** - Dock simgesinin üzerine gelince açık pencerelerin canlı önizlemesi; tıklayarak geç veya önizlemeden kapat / küçült / tam ekran yap
- **Option + Tab pencere geçişi** - Windows'taki Alt+Tab gibi tüm açık pencereleri canlı önizlemeli listeler
- **Cmd + Tab geliştirmesi** - Yerleşik uygulama geçişine pencere önizlemeleri ekler (isteğe bağlı)
- **Önizlemeden pencere kontrolü** - Trafik ışığı düğmeleri, orta tıkla kapatma, sürükleyerek taşıma
- **Dock kilitleme** - Çoklu monitörde Dock'un belirli bir ekranda sabit kalması
- **Trackpad hareketleri** - Önizleme açıkken iki parmakla Dock'a doğru kaydır = küçült, uzaklaştır = tam ekran
- **Aero çalkala** - Önizlemede pencereyi sallayarak aynı uygulamanın diğer pencerelerini küçült
- **Hızlı uygulama kapatma** - `Cmd + sağ tık` ile Dock'tan uygulamayı kapat
- **Dock simgesine tekrar tıkla = gizle** - Uygulamayı öne getirdikten sonra tekrar tıklayınca tüm pencereleri gizle veya küçült
- **Müzik widget'ı** - Spotify, Apple Music ve YouTube için Dock üzerinde medya kontrolleri; sabitleyerek ekranda tut
- **Takvim entegrasyonu** - Takvim uygulamasının Dock simgesine gelince günün etkinliklerini gör
- **Folder Pop** - Dock klasörlerinin içeriğini önizle
- **Görünüm özelleştirme** - Önizleme düzeni, boyut, arka plan, saydamlık, kompakt liste modu
- **Gizlilik** - %100 yerel; izleme, analitik ve otomatik çökme raporu yok

---

## 📥 İndirme ve Kurulum

### Yöntem 1: Homebrew (Önerilen)

```bash
brew install --cask dockdoor
```

> Homebrew yüklü değilse: [brew.sh](https://brew.sh) adresindeki komutu Terminal'de çalıştır.

### Yöntem 2: Resmi İndirme

1. [dockdoor.net](https://dockdoor.net/) adresine git
2. Sağ üstten **Download** → **Download for Mac** ile `.dmg` indir
3. DockDoor'u **Applications** klasörüne sürükle
4. Gatekeeper uyarısı çıkarsa: Sistem Ayarları → Gizlilik ve Güvenlik → Yine de Aç

> ⚠️ Yalnızca [dockdoor.net](https://dockdoor.net/) veya [github.com/ejbills/DockDoor](https://github.com/ejbills/DockDoor) resmi kaynaklarından indir. Erişilebilirlik ve ekran kaydı izni gerektirdiği için üçüncü taraf sitelerden indirilen sürümler ciddi güvenlik riski taşır.

---

## ⚙️ İlk Kurulum ve Önerilen Ayarlar

1. **Erişilebilirlik izni (zorunlu):** İlk açılışta macOS izin ister → Sistem Ayarları → Gizlilik ve Güvenlik → Erişilebilirlik → DockDoor'u etkinleştir
2. **Ekran kaydı izni (önizleme için gerekli):** Pencere önizlemeleri için **Sistem Ayarları → Gizlilik ve Güvenlik → Ekran ve Sistem Ses Kaydı** → DockDoor'u ekle. Listede görünmüyorsa sol alttaki **+** ile Applications klasöründen DockDoor'u seç → **Quit & Reopen** → **Allow** → uygulamayı yeniden başlat
3. **Girişte başlat:** **Settings → General** → **Launch at login**
4. **Menü simgesini gizle (isteğe bağlı):** **Settings → General** → **Show menu bar icon** kapat - uygulamaya Spotlight ile erişebilirsin

> 💡 Erişilebilirlik izni olmadan uygulama çalışmaz. Ekran kaydı izni vermezsen Dock önizlemeleri ve geçiş aracındaki canlı küçük resimler görünmez; diğer bazı işlevler sınırlı kalabilir.

---

## 🚀 Temel Kullanım

### Dock önizlemeleri

1. Dock'taki herhangi bir uygulama simgesinin üzerine gel
2. O uygulamaya ait tüm açık pencereler canlı önizleme olarak açılır
3. İstediğin pencereye tıkla - tıklamadan önce ne açacağını görürsün
4. Önizleme üzerindeki trafik ışığı düğmeleriyle kapat, küçült veya tam ekran yap

**Önerilen ayarlar** - **Settings → Dock Previews:**

| Ayar | Ne işe yarar |
| ---- | ------------ |
| Yalnızca mevcut Space'teki pencereler | Sanal masaüstünde (Space) yalnızca bulunduğun Space'teki pencereleri göster |
| Yalnızca mevcut monitördeki pencereler | İki monitörde aynı uygulamanın pencereleri varsa yalnızca imlecin olduğu ekrandakileri listele |
| **Simulate a click** (Bir tıklamayı taklit et) | Önizleme üzerinde durunca pencereyi doğrudan aç |
| **Show full-size preview** | Önizleme üzerinde durunca pencereyi tam boyutta göster; imleci çekince geri gider |
| **Delay** | Yukarıdaki etkileşimin ne kadar hızlı tetikleneceğini ayarla |
| **Hide all app windows on dock icon click** | Dock simgesine tekrar tıklayınca uygulamayı gizle veya küçült |

**Hızlı uygulama kapatma:** `Cmd` basılı tutup Dock'ta uygulamaya **sağ tık** → uygulamayı kapat (`Cmd + Q` ile aynı). İnatçı uygulamalar için `Cmd + Option + sağ tık` ile zorla kapat.

### Option + Tab pencere geçişi

1. `Option + Tab` tuşlarına bas ve **Option**'ı basılı tut
2. **Tab** ile ileri, **Shift + Tab** ile geri git (ok tuşları da çalışır)
3. **Return** ile seçili pencereye geç
4. Önizlemeden `Cmd + W` kapat, `Cmd + Q` çık, `Cmd + M` küçült

Varsayılan ayarlar çoğu kullanıcı için yeterlidir. Görünümü değiştirmek için **Settings → Window Switcher** ve **Settings → Appearance** sekmelerine bak.

### Cmd + Tab geliştirmesi

1. **Settings → Cmd+Tab** → üstten özelliği etkinleştir
2. Uygulama yeniden başlatılması istenir → **OK** de
3. Artık `Cmd + Tab` ile uygulama simgelerinin yanında canlı pencere önizlemeleri görünür
4. Örnek: Safari'nin üç penceresi açıkken `Cmd + Tab` ile Safari'ye gel, `Cmd`'den elini kaldırmadan **A** tuşuna bas - pencereler arasında seçim yap

İstemezsen aynı sekmeden kapatabilirsin.

### Dock kilitleme (çoklu monitör)

1. **Settings → Dock Locking** → özelliği etkinleştir
2. Yeniden başlatma uyarısında **OK**
3. Tekrar **Dock Locking** sekmesine dön → Dock'un sabitleneceği monitörü seç

İmleci ekran altına götürünce Dock'un diğer monitöre atlamasını engeller. "Displays have separate Spaces" açıkken en iyi çalışır.

### Trackpad hareketleri

Dock önizlemesi açıkken:

- **İki parmakla Dock'a doğru kaydır** → pencere küçülür (gizlenir)
- **Dock'tan uzağa kaydır** → tam ekran

Özelleştirmek için **Settings → Gestures & Keybinds**.

### Aero çalkala

Dock veya `Cmd + Tab` önizlemesinde bir pencereyi tutup sallarsan aynı uygulamanın **diğer tüm pencereleri** otomatik küçülür.

**Settings → Gestures & Keybinds → Aero Shake** → *Minimize all windows except current* (veya istediğin davranış).

### Orta tıkla pencere kapatma

Önizlemedeki herhangi bir pencerenin üzerine **orta tık** (mouse tekerleği) ile tıklayarak o uygulamaya geçmeden pencereyi kapatabilirsin.

**Settings → Gestures & Keybinds → Mouse Actions → Middle click** ile davranışı değiştir (kapat, küçült vb.).

### Müzik widget'ı

1. Dock'ta Spotify, Apple Music veya YouTube simgesinin üzerine gel
2. Medya kontrollerini gör - oynat, duraklat, ileri sar
3. Kontrollerin üzerine **sağ tık** → **Full** veya **Compact** mod ile ekrana sabitle; konumlandır
4. Kapatmak için yine sağ tık → **Close**

Ayarlar: **Settings → Filters & Widgets** (veya **Widgets** sekmesi).

### Görünüm ayarları

**Settings → Appearance** altında önizlemelerin en-boy oranı, arka plan, boşluk, saydamlık ve trafik ışığı düğmelerinin görünürlüğünü ayarlayabilirsin. Mor düğme uygulamayı tamamen kapatır (`Cmd + Q` ile aynı).

Eski ince görünüm için **Settings → Dock Previews** → *Allow dynamic image sizing*, *Embed controls in preview frames* ve isteğe bağlı *Dock styling on traffic light buttons* kapat.

### Klavye kısayolları

| Kısayol | İşlev |
| ------- | ----- |
| `Option + Tab` (basılı tut) | Pencere geçiş aracını aç |
| `Tab` / `Shift + Tab` | İleri / geri |
| `↑` `↓` `←` `→` | Pencere geçişinde gezin |
| `Return` | Seçili pencereye geç |
| `Cmd + W` | Pencereyi kapat |
| `Cmd + Q` | Uygulamayı kapat |
| `Cmd + M` | Küçült |
| `Cmd + sağ tık` (Dock) | Uygulamayı Dock'tan kapat |

Kısayollar **Settings → Gestures & Keybinds** altından özelleştirilebilir.

---

## ⚠️ Bilinen Sorunlar ve Çözümleri

| Sorun | Neden Olur | Çözüm |
| ----- | ---------- | ----- |
| Önizlemeler görünmüyor | Ekran kaydı izni yok | Sistem Ayarları → Ekran ve Sistem Ses Kaydı → DockDoor ekle; uygulamayı yeniden başlat |
| Kısayol çalışmıyor | Erişilebilirlik izni yok | Sistem Ayarları → Erişilebilirlik → DockDoor açık olsun |
| Ekran kaydında DockDoor listede yok | macOS izin listesinde henüz görünmüyor | Sol alttaki **+** ile Applications'tan DockDoor'u manuel ekle |
| `Option + Tab` çakışması | AltTab veya başka uygulama aynı kısayolu kullanıyor | Bir uygulamada kısayolu değiştir veya diğerini devre dışı bırak |
| Bazı uygulamalar önizlenmiyor | Özel UI framework kullanan uygulamalar | Bilinen sınırlama; standart macOS uygulamalarında sorunsuz çalışır |
| Dock kilitleme tutarsız | Space / monitör ayarları | Sistem Ayarları'nda "Displays have separate Spaces" açık olsun |

---

## 🔗 Faydalı Bağlantılar

- 🌐 [Resmi Web Sitesi](https://dockdoor.net/)
- 💾 [GitHub Sayfası](https://github.com/ejbills/DockDoor)
- 📖 [Resmi Dokümantasyon](https://dockdoor.net/) *(site içi Docs)*
- 🎬 [Kolay Bilgi - YouTube inceleme / tanıtım](https://www.youtube.com/watch?v=CcB9H7Kw6kk&t=92s)
- 📦 [Homebrew Cask](https://formulae.brew.sh/cask/dockdoor)
- 💝 [Geliştirmeyi destekle](https://dockdoor.net/)

---

## 📝 Notlar

> DockDoor, macOS Dock'unu koruyarak Windows'tan aşina olunan pencere önizleme ve geçiş deneyimini ücretsiz sunar. Yalnızca `Option + Tab` ile pencere geçişi istiyorsan [AltTab](AltTab.md) daha odaklı bir alternatiftir; Dock hover önizlemesi de istiyorsan DockDoor belirgin avantaj sağlar. İkisini birlikte kurduysan `Option + Tab` çakışmasına dikkat et. **DockDoor Pro** ayrı bir uygulamadır ve yerleşik Dock'u tamamen değiştirir - bu rehberdeki ücretsiz sürümle karıştırma.

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

*Son güncelleme: 2026-06-17*
