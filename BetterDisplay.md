# 🛠️ BetterDisplay

> **Kısa Açıklama:** Mac'te ekran çözünürlüğü, HiDPI ölçekleme, XDR/HDR parlaklık, DDC kontrolü, sanal ekranlar ve çoklu monitör yönetimini menü çubuğundan sunan kapsamlı bir ekran yönetim aracı.

v4.3.4 · macOS Ventura 13.2+ / Sonoma / Sequoia / Tahoe (Apple Silicon / Intel) · Freemium (Free + Pro) · Ekran yönetimi

---

## 📌 Genel Bakış

BetterDisplay, macOS'un yerleşik **Displays** ayarlarının yetersiz kaldığı noktalarda devreye girer: harici monitörlerde esnek HiDPI ölçekleme, XDR/HDR ekstra parlaklık, DDC ile donanım parlaklık/ses/giriş kontrolü, sanal ekran oluşturma ve ekranları yazılımsal olarak bağlantıdan çıkarma gibi gelişmiş işlemler sunar. [@waydabber](https://github.com/waydabber) tarafından geliştirilen uygulama, [MonitorControl](https://formulae.brew.sh/cask/monitorcontrol) ile benzer DDC özellikleri paylaşsa da çözünürlük, sanal ekran, EDID ve XDR tarafında çok daha geniş bir kapsama sahiptir. Ücretsiz sürümde birçok temel özellik kullanılabilir; gelişmiş işlevler **Pro** lisansı veya 14 günlük deneme ile açılır.

---

## 🖥️ Harici monitörde bulanık yazılar (HiDPI) sorunu

MacBook'un dahili ekranı genelde keskin ve net görünür; harici monitör takınca yazılar bulanık, ikonlar pürüzlü kalabilir. Bu fark çoğu zaman **HiDPI (Retina ölçekleme)** kaynaklıdır.

### Sorun neden oluşur?

| Mod | Nasıl çalışır | Görünüm |
| --- | ------------- | ------- |
| **Normal (1:1)** | Her fiziksel piksel = bir mantıksal piksel (ör. 1920×1080) | Büyük ekranda veya yakından bakınca pikseller seçilir; yazı köşeleri tırnaklı |
| **HiDPI (Retina)** | Sistem daha yüksek çözünürlükte render eder, sonra 2× küçültür (ör. 3840×2160 → 1920×1080 mantıksal) | Her mantıksal pikselin arkasında birden fazla gerçek piksel; çok daha keskin metin |

Apple dahili MacBook ekranlarında HiDPI'yi otomatik kullanır. Harici monitörlerde ise macOS, Apple'ın eşik kurallarına göre HiDPI'yi çoğu zaman **açmaz** - özellikle 1080p gibi düşük fiziksel çözünürlüklerde.

### BetterDisplay bunu nasıl çözer?

BetterDisplay, sistem çözünürlüğünden **daha yüksek bir sanal çözünürlük** oluşturur ve bunu **2× ölçekleyerek** HiDPI benzeri keskinliği etkinleştirir.

**Örnek:** 1920×1080 fiziksel monitörde uygulama 2560×1440 gibi bir sanal mod oluşturur; bunu 1280×720 mantıksal olarak gösterir ama arkada gerçek piksel yoğunluğu korunur. Sonuç: 1080p monitörde Retina'ya yakın, belirgin şekilde daha keskin bir görüntü.

> Ayarı açtığında çözünürlük değiştirirken olduğu gibi kısa bir takılma normaldir; genelde daha hafiftir.

---

## ✨ Öne Çıkan Özellikler

### Ücretsiz sürümde de kullanılabilenler

- **Menü çubuğu arayüzü** - Tüm ekranları tek yerden yönet; çözünürlük, yenileme hızı ve döndürme menüleri
- **Çok yöntemli parlaklık kontrolü** - Yazılımsal karartma, yerleşik klavye tuşları ve temel DDC desteği
- **DDC desteği** - Apple Silicon dahil modern Mac'lerde harici monitör parlaklık/ses kontrolü (dock/dongle uyumluluğu monitöre bağlı)
- **TV ağ kontrolü** - LG webOS, Samsung Tizen, Philips Android TV ve Yamaha AVR desteği
- **Sanal ekran oluşturma** - Farklı çözünürlük ve en-boy oranlarında sanal monitörler
- **EDID bilgisi** - Bağlı ekranların ayrıntılı bilgilerini görüntüle ve dışa aktar
- **Temel klavye kısayolları** - Parlaklık ve ses için özelleştirilebilir kısayollar
- **macOS Shortcuts** - App Intents ile otomasyon desteği

### Pro lisansı gerektirenler (*)

- **Esnek HiDPI ölçekleme** - Gerçek ekranları tam ölçeklenebilir Retina moduna dönüştürme
- **XDR/HDR ekstra parlaklık** - Dahili veya harici HDR ekranlarda 1600 nit'e kadar upscaling
- **Özel çözünürlükler** - Favori çözünürlükler, çözünürlük kaydırıcısı ve klavye kısayolları
- **Yazılımsal bağlantı kesme** - Ekranları fiziksel olarak sökmeden düzen dışına alma / geri ekleme
- **Picture in Picture ve yerel akış** - Ekran içeriğini başka bir ekrana yönlendirme, teleprompter modu
- **EDID override** - Intel ve Apple Silicon Mac'lerde ekran tanımlayıcısını geçersiz kılma
- **Ekran yapılandırma koruması** - Çözünürlük, yenileme hızı/VRR, döndürme ve renk profili kilitleme
- **Ekran grupları ve senkronizasyon** - Çoklu monitörde parlaklık, nit bazlı eşitleme ve UI ölçeği eşleme
- **Renk modu seçici** - Apple Silicon'da RGB, YCbCr, chroma subsampling ve HDMI aralığı
- **Komut satırı ve entegrasyon** - `betterdisplaycli`, özel URL şeması, HTTP ve bildirimler
- **Gelişmiş düzen yönetimi** - Anchor noktalarıyla layout protection, ayna yapılandırması

> Pro lisansı kalıcıdır (abonelik değil): **$21.99 / €19.99** - en az bir yıl ücretsiz güncelleme dahil. İş kullanımında deneme sonrası lisans gerekir.

---

## 📥 İndirme ve Kurulum

### Yöntem 1: Homebrew (Önerilen)

```bash
brew install --cask betterdisplay
```

> Homebrew yüklü değilse: [brew.sh](https://brew.sh) adresindeki komutu Terminal'de çalıştır.

Kurulum sonrası CLI aracı `betterdisplaycli` komutu olarak da kullanılabilir.

### Yöntem 2: Resmi İndirme

1. [betterdisplay.pro](https://betterdisplay.pro/) adresine git
2. **Download** ile güncel **v4.x** sürümünü indir (.dmg)
3. BetterDisplay'i **Applications** klasörüne sürükle
4. Gatekeeper uyarısı çıkarsa: Sistem Ayarları → Gizlilik ve Güvenlik → Yine de Aç

**macOS sürümüne göre:**

| macOS | Önerilen sürüm |
| ----- | -------------- |
| Tahoe 26, Sequoia, Sonoma, Ventura 13.2+ | v4.x (güncel) |
| Monterey | v2.3.9 |
| Mojave, Catalina, Big Sur | v1.4.15 |

---

## ⚙️ İlk Kurulum ve Önerilen Ayarlar

1. **Erişilebilirlik izni:** İlk açılışta macOS güvenlik uyarısı çıkar → **Aç** de. Tüm özellikler için **Sistem Ayarları → Gizlilik ve Güvenlik → Erişilebilirlik** altında BetterDisplay'i etkinleştirmen gerekebilir
2. **Menü çubuğu simgesi:** Uygulama açıldığında menü çubuğundaki BetterDisplay simgesine tıkla; MacBook ekranı ve bağlı harici monitörler otomatik listelenir. Her ekranın altında o ekrana özel ayarlar görünür
3. **Girişte başlat:** Menü → **Settings** (dişli) → **Application** → **Launch at login**
4. **DDC yapılandırması (harici monitör parlaklığı):** **Settings → Displays** → üstten harici monitörü seç → **Enable DDC control** aç → **Configure DDC controls** → **Detect DDC capabilities** ile monitörün donanım desteğini öğren
5. **HiDPI / yüksek çözünürlük:** Harici monitör menüsünü genişlet → **High resolution** / **Yüksek çözünürlük** (veya **Flexible scaling**) seçeneğini aç - değişiklik anında fark edilir *(Pro özelliği; ayrıntı yukarıdaki HiDPI bölümünde)*
6. **Pro denemesi:** **Settings → Pro** - 14 günlük tam özellik denemesini başlat veya lisansını gir
7. **Yalnızca ücretsiz özellikleri denemek için:** **Settings → Application → Advanced settings and privacy** → **Licensing and Pro features** kapat - 14 günlük deneme aktif olsa bile uygulamayı sadece ücretsiz katmanla kullanırsın; hangi özelliğin Pro'ya bağlı olduğunu böyle test edebilirsin
8. **Güncellemeler:** **Settings → Application → Updates** - beta sürümler için *Receive Internal Pre-Release* (yalnızca macOS beta kullanıcıları)

> 💡 Aynı makinede **MonitorControl** de yüklüyse ikisi de DDC kullanabilir; çakışma yaşarsan birini devre dışı bırak veya BetterDisplay'de DDC'yi yalnızca ihtiyaç duyduğun ekranlar için aç.

---

## 🚀 Temel Kullanım

### Harici monitör parlaklığı (F1/F2 ve DDC)

MacBook'un dahili ekranında F1/F2 parlaklığı değiştirir; harici monitörlerde varsayılan macOS bunu yapmaz. BetterDisplay ile:

1. Ekran menüsünde **Brightness** kaydırıcısını kullan
2. **Settings → Keyboard shortcuts** ile F1/F2'yi harici monitöre yönlendir - videodaki gibi klavye tuşlarıyla harici parlaklık ayarlanabilir
3. Monitör DDC'yi donanımsal desteklemiyorsa parlaklık **yazılımsal karartma** ile simüle edilir (donanım kontrolünden daha az ideal ama işlevsel)

**DDC desteğini kontrol etme:**

1. **Settings → Displays** → harici monitörü seç
2. **Enable DDC control** açık olsun
3. **Configure DDC controls** → **Detect DDC capabilities**
4. Dock veya USB-C hub üzerinden bağlıysan DDC çalışmayabilir; mümkünse doğrudan Mac portuna bağla

### Çözünürlük ve yenileme hızı değiştirme

1. Menü çubuğundaki BetterDisplay simgesine tıkla
2. İlgili ekranı seç
3. **Resolution** menüsünden istediğin modu seç - **Sistem Ayarları'na girmeden** hızlı geçiş yapılır
4. BetterDisplay, macOS'un gizlediği çözünürlükleri de listeler. Sistem Ayarları'nda yalnızca birkaç seçenek görürsün; orada sağ tık → **Listeyi göster** ve alttan **Tüm çözünürlükleri göster** ile daha fazlasını açabilirsin, ancak BetterDisplay çoğu kullanıcı için daha pratiktir
5. Ekran menüsünü genişlet (alt ok) → **Refresh rate** ile yenileme hızını değiştir
6. Pro'da **Resolution slider** veya tanımladığın klavye kısayolu ile hızlı geçiş yap

### HiDPI / yüksek çözünürlük (bulanık yazı çözümü)

1. Menü çubuğundan BetterDisplay simgesine tıkla
2. Harici monitörü bul ve ayarları genişlet
3. **High resolution** / **Yüksek çözünürlük** (menüde **Flexible scaling** olarak da geçebilir) üzerine bir kez tıkla - ayar anında etkinleşir
4. İstersen aynı menüden monitörü **ana ekran** olarak işaretle

> **Pro notu:** Esnek HiDPI ölçekleme resmi olarak **Pro** lisansına bağlıdır. Ücretsiz katmanda nelerin açık olduğunu görmek için yukarıdaki *Licensing and Pro features* kapatma adımını kullan. 14 günlük deneme süresince tüm özellikler test edilebilir.

### Ekran yerleşimi ve döndürme

- **Move screen / Ekranı taşı:** Çoklu monitörde fiziksel konumu ayarla (Sistem Ayarları → Ekranlar → Yerleşim ile de yapılır; uygulama tarafında sorun olursa sistem ayarlarından düzelt)
- **Rotate display / Ekranı döndür:** Monitörü dikey (portrait) kullanmak için görüntüyü 90° döndür

### Sanal ekran oluşturma

1. Menü → **Create virtual screen**
2. Çözünürlük ve en-boy oranını belirle
3. Headless Mac, Sidecar alternatifi veya uzaktan erişim senaryolarında sanal ekranı hedef çözünürlükle kullan

### Ekranı yazılımsal olarak bağlantıdan çıkarma (Pro)

1. Ekran menüsünde **Disconnect display** seç
2. Ekran düzeninden kaldırılır; fiziksel kablo takılı kalır
3. Geri eklemek için **Connect display**

### Komut satırı (`betterdisplaycli`)

Homebrew kurulumunda CLI wrapper olarak gelir:

```bash
betterdisplaycli --help
```

Ayrıntılı komut listesi ve otomasyon örnekleri için [GitHub Wiki](https://github.com/waydabber/BetterDisplay/wiki) bölümüne bak.

### Klavye kısayolları

Kısayollar tamamen özelleştirilebilir; varsayılanlar kuruluma göre değişir. **Settings → Keyboard shortcuts** altından parlaklık, ses, çözünürlük ve ekran grupları için atama yap.

| Kısayol | İşlev |
| ------- | ----- |
| *(özelleştirilebilir)* | Parlaklık artır / azalt |
| *(özelleştirilebilir)* | Favori çözünürlüğe geç (Pro) |
| *(özelleştirilebilir)* | Ekran döndürme |
| macOS yerleşik | F1/F2 - BetterDisplay'e yönlendirilerek harici monitör parlaklığı |

### Menü çubuğu özelleştirme

Menüde kullanmadığın birçok seçeneği gizleyerek arayüzü sadeleştirebilirsin.

**Simge görünümü**

1. **Settings → Menu** → **Additional menu bar icon options**
2. **Match menu icon to main display icon** - menü simgesi ana ekranın simgesiyle eşleşir
3. **Customize app icon** → **Browse** ile alternatif simgelerden birini seç; **Remove** ile varsayılan simgeye dön
4. Menü simgesini istemiyorsan üstteki **Show app icon in menu bar** kapat - uygulamaya Spotlight ile erişebilirsin

**Menü içeriğini sadeleştirme**

1. **Settings → Menu** → **Customize menu options** → **Customize app menu content**
2. Kullanmayacağın öğeleri **Hidden** yap
3. Sık kullanılanlar: **Brightness**, **Resolution**, **Toggle** (yüksek çözünürlük ve ana ekran geçişlerini tek tıkla aç/kapat)
4. Eski düzeni geri almak için **Reset menu layout**

---

## ⚠️ Bilinen Sorunlar ve Çözümleri

| Sorun | Neden Olur | Çözüm |
| ----- | ---------- | ----- |
| Harici monitörde yazılar bulanık | macOS harici ekranda HiDPI açmıyor | Ekran menüsünden **High resolution** / **Flexible scaling** aç (Pro); açıklama için yukarıdaki HiDPI bölümüne bak |
| DDC parlaklık çalışmıyor | Dock, hub veya DisplayLink aracılığı | Monitörü doğrudan Mac portuna bağla; **Settings → Displays** → **Detect DDC capabilities** ile yeniden algıla |
| Esnek ölçekleme seçeneği yok | Pro lisansı veya macOS sürümü | Pro etkinleştir; macOS Monterey 12.4+ ve natively bağlı ekran gerekir |
| Disconnect sonrası ekran geri gelmiyor (Intel) | Intel'de deneysel özellik | Apple Silicon + Ventura önerilir; Intel'de dikkatli kullan |
| MonitorControl ile çakışma | İki uygulama aynı DDC kanalını kullanıyor | Bir uygulamada DDC'yi kapat veya yalnızca birini aktif tut |
| XDR upscaling etkisiz | Uyumsuz ekran veya SDR modu | XDR/HDR uyumlu ekran ve Pro lisansı gerekir; **Settings → XDR/HDR** kalibrasyonunu kontrol et |
| Yenileme hızı menüsünde eksik modlar | macOS'un göstermediği modlar | Pro **Unexposed refresh rates** ve **Forced HDR mode** seçeneklerini dene |

---

## 🔗 Faydalı Bağlantılar

- 🌐 [Resmi Web Sitesi](https://betterdisplay.pro/)
- 💾 [GitHub Sayfası](https://github.com/waydabber/BetterDisplay)
- 📖 [GitHub Wiki (kullanım ve CLI)](https://github.com/waydabber/BetterDisplay/wiki)
- 🗣️ [GitHub Discussions](https://github.com/waydabber/BetterDisplay/discussions)
- 🎬 [Kolay Bilgi - YouTube inceleme / tanıtım](https://www.youtube.com/watch?v=VzQN47UOq50)
- 📦 [Homebrew Cask](https://formulae.brew.sh/cask/betterdisplay)
- 💳 [Pro lisans satın alma](https://betterdisplay.pro/)

---

## 📝 Notlar

> BetterDisplay, çoklu monitör ve harici ekran kullanan Mac kullanıcıları için en kapsamlı seçeneklerden biridir. Harici 1080p monitörde MacBook kadar keskin metin istiyorsan asıl fark **HiDPI / yüksek çözünürlük** özelliğindedir - bu, resmi dokümantasyonda **Pro** kapsamındadır. Yalnızca harici monitör parlaklığı istiyorsan MonitorControl daha hafif bir alternatiftir; çözünürlük, HiDPI, sanal ekran veya XDR parlaklık ihtiyacın varsa BetterDisplay belirgin şekilde daha güçlüdür. Ücretsiz sürümde parlaklık, çözünürlük değiştirme ve temel DDC gibi birçok işlev vardır; hangi özelliğin ücretsiz olduğunu **Licensing and Pro features** kapatılarak denenebilir. Raycast kullanıcıları için resmi BetterDisplay eklentisi de mevcuttur.

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
