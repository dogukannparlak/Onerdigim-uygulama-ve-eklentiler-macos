# 🛠️ ClearDisk

> **Kısa Açıklama:** Geliştirici önbelleklerini (Xcode, Homebrew, npm, Docker, Cursor vb.) menü çubuğundan tarayıp güvenli şekilde temizleyen; risk seviyeleri ve Çöp Kutusu'na taşıma ile disk alanı kazandıran ücretsiz, açık kaynaklı araç.

v1.7.1 · macOS 14+ · Apple Silicon · MIT / açık kaynak · Disk / geliştirici araçları

---

## 📌 Genel Bakış

Aktif geliştirme yapan bir Mac'te Xcode DerivedData, Homebrew cache, `node_modules`, Docker imajları ve paket yöneticisi önbellekleri hızla onlarca hatta yüzlerce GB kaplayabilir. [OnyX](OnyX.md) ve [Mac Sai](MacSai.md) genel sistem bakımına odaklanır; **ClearDisk** ise yalnızca **63 bilinen geliştirici önbellek yolunu** tarar ve hangisinin güvenle silinebileceğini açıklar.

Menü çubuğunda disk kullanımını gösterir; %80 / %90 eşiklerinde renk değiştirir ve temizlenebilir alanı bildirir. Silinen dosyalar doğrudan yok edilmez - **Çöp Kutusu'na taşınır**; geri almak mümkündür. Ağ erişimi, telemetri ve analitik yoktur; kaynak kodu açıktır. Genel amaçlı temizlik için Mac Sai veya OnyX; uygulama kaldırma için [AppCleaner](AppCleaner.md) ile birlikte düşün.

> Şu an **Apple Silicon** ve **macOS 14+** desteklenir. Intel Mac desteği gelecek sürümlerde planlanıyor olabilir.

---

## ✨ Öne Çıkan Özellikler

- **63 geliştirici önbelleği** - Xcode (DerivedData, Archives, Simulators…), Swift PM, CocoaPods, Homebrew, npm/Yarn/pnpm/Bun/Deno, pip/UV/Conda, Gradle/Maven, Docker, Go, Cargo, JetBrains, VS Code / **Cursor**, AI araçları (Claude, Ollama, HuggingFace…), Playwright, Unity/Godot ve daha fazlası
- **Proje tarayıcısı** - Eski `node_modules`, `target/`, `.build/`, `build/`, `vendor/` klasörlerini 11 proje tipinde bulur
- **Risk seviyeleri** - 🟢 Güvenli (komutla yeniden oluşur), 🟡 Dikkat (büyük yeniden indirme), 🔴 Riskli (geri dönüşü zor veri)
- **Önbellek açıklamaları** - Her kategori ne işe yaradığını ve silince ne olacağını Türkçe/İngilizce açıklar
- **DerivedData dökümü** - Hangi projenin ne kadar yer kapladığını proje adıyla gösterir
- **Hero panel** - Temizlenebilir alan, güvenli miktar çubuğu ve **Clean Caches** düğmesi
- **Menü çubuğu monitörü** - Anlık disk doluluk oranı; stresli diskte temizlenebilir miktar
- **Depolama tahmini** - 90 günlük trende göre diskin ne zaman dolacağını öngörür
- **Akıllı öneriler** - Yaşa dayalı temizlik tavsiyeleri (ör. 90 gündür kullanılmayan)
- **Xcode uyarısı** - Xcode açıkken ilgili önbellekleri temizlemeye çalışınca uyarır
- **Güvenli silme** - Kalıcı silme yok; her şey önce Çöp Kutusu'na gider
- **Gizlilik** - Sıfır ağ erişimi, telemetri yok; ~590 KB, harici bağımlılık yok

---

## 📥 İndirme ve Kurulum

### Yöntem 1: Homebrew (Önerilen)

ClearDisk özel bir tap gerektirir:

```bash
brew tap bysiber/cleardisk
brew install --cask cleardisk
```

Güncelleme:

```bash
brew update
brew upgrade --cask cleardisk
```

> Homebrew yüklü değilse: [brew.sh](https://brew.sh) adresindeki komutu Terminal'de çalıştır.

### Yöntem 2: GitHub Releases

1. [GitHub Releases](https://github.com/bysiber/cleardisk/releases/latest) sayfasından `.dmg` indir
2. ClearDisk'i **Applications** klasörüne sürükle
3. **İlk açılış (notarize edilmemiş):** Uygulama engellenirse Sistem Ayarları → Gizlilik ve Güvenlik → **Yine de Aç**
4. GUI işe yaramazsa Terminal'de:

```bash
xattr -cr /Applications/ClearDisk.app
```

> ClearDisk Apple notarizasyonu kullanmaz (ücretli geliştirici hesabı). Uygulama açık kaynaklıdır - kaynak kodu denetlenebilir.

### Yöntem 3: Kaynaktan derleme

```bash
git clone https://github.com/bysiber/cleardisk.git
cd cleardisk
bash scripts/build_app.sh
cp -R ClearDisk.app /Applications/
xattr -cr /Applications/ClearDisk.app
open /Applications/ClearDisk.app
```

Kaynak derleme için Xcode Command Line Tools gerekir: `xcode-select --install`

---

## 🖥️ Arayüz

Menü çubuğundaki disk simgesine tıklayınca açılan panel dört bölümden oluşur:

### Üst bar (her sekmede)

| Öğe | İşlev |
| --- | ----- |
| **ClearDisk** başlığı | Uygulama adı |
| ⚙️ **Ayarlar** | Tercihler (girişte başlat, bildirimler vb.) |
| 🔄 **Yenile** | Taramayı hemen yeniden başlat |
| **Disk çubuğu** | Doluluk yüzdesi (ör. %31), **kullanılan GB** / **boş GB** |
| **Forecast** | Depolama tahmini; yeterli anlık görüntü yoksa `collecting data... (N snapshots)` yazar - birkaç gün kullanınca doluluk tahmini oluşur |

### Hero alanı (temizlenebilir alan)

| Öğe | İşlev |
| --- | ----- |
| **XXX MB reclaimable space found** | Toplam temizlenebilir geliştirici önbelleği |
| Yeşil çubuk + **XXX MB safe** | Güvenli (🟢) olarak işaretlenen kısmın özeti |
| **Clean Caches** | Tüm güvenli önbellekleri tek seferde **Çöp Kutusu'na** taşır |

> **Clean Caches** yalnızca **Developer** sekmesindeki önbellekleri hedefler; **Large Files** veya **Overview** içeriğini silmez.

### Sekmeler

| Sekme | İçerik |
| ----- | ------ |
| **Developer** | Geliştirici önbellekleri - gruplu liste (AI Tools, JetBrains, Homebrew, Xcode vb.) |
| **Projects** | Proje klasörlerindeki eski `node_modules`, `target/`, `.build/` vb. artıklar; tarama yolları: `~/Documents`, `~/Developer`, `~/Projects`, `~/Code`, `~/Desktop` |
| **Overview** | Sistem geneli kategori dökümü (Applications, Movies, Documents…) + **Storage Trend** grafiği |
| **Large Files** | Büyük dosya kategorileri; chevron ile genişletilip tek tek incelenir |

Sağ alttaki **↗** simgesi paneli genişletilmiş pencere modunda açar.

### Alt bar

| Öğe | İşlev |
| --- | ----- |
| **Total saved: X GB** | Kurulumdan bu yana kümülatif kurtarılan alan |
| **Quit** | ClearDisk'i kapat |

---

## ⚙️ İlk Kurulum ve Önerilen Ayarlar

1. **İlk tarama:** Menü çubuğundaki disk simgesine tıkla - 5 dakikalık aralıkla bilinen önbellek yolları taranır (tam disk taraması yapmaz)
2. **Girişte başlat (isteğe bağlı):** ClearDisk ayarlarından oturum açılışında başlat; menü çubuğunda disk monitörü sürekli görünsün
3. **Thaw ile birlikte:** Menü çubuğu simgesini [Thaw](Thaw.md) **Gizli** bölümüne taşı - disk yüzdesi gerektiğinde tıklama/kaydırma ile açılır
4. **Bildirimler:** %80 ve %90 disk eşik bildirimlerini açık bırak; spam yapmaz
5. **Temizlik öncesi:** Xcode kullanıyorsan kapat; Docker temizliğinde 🔴 **Riskli** etiketli öğeleri dikkatle oku

> 💡 ClearDisk genel sistem temizliği yapmaz. Launch Services, Mail ekleri veya uygulama kaldırma için [OnyX](OnyX.md) veya [Mac Sai](MacSai.md) kullan.

---

## 🚀 Temel Kullanım

### Developer - geliştirici önbelleklerini temizleme

1. Menü çubuğundaki ClearDisk simgesine tıkla
2. Varsayılan **Developer** sekmesinde **Developer Caches** listesini incele
3. Her satırda şunlar görünür:
   - **Grup adı** (ör. AI Tools, JetBrains Cache, Homebrew Cache)
   - **Son kullanım** (ör. `0d ago`)
   - **Dosya yolu** (ör. `~/Library/Caches/Homebrew`)
   - **Açıklama** - silince ne olacağını anlatır (ör. *"Re-downloads on brew install."*)
   - **Boyut** - satırın sağında
   - 🗑️ **Tek öğe temizle** · 📁 **Finder'da aç**
4. Yalnızca güvenli olanları toplu silmek için **Clean Caches** kullan
5. Belirli bir önbelleği hedeflemek için satırdaki 🗑️ simgesine tıkla

**Örnek gruplar (sisteminde bulunanlara göre değişir):**

| Grup | Örnek | Tipik açıklama |
| ---- | ----- | -------------- |
| **AI Tools** | Cursor Cache | Cursor / AI araç önbelleği |
| **JetBrains Cache** | `~/Library/Caches/JetBrains` | IDE yeniden başlayınca oluşur |
| **Homebrew Cache** | `~/Library/Caches/Homebrew` | `brew install` ile yeniden indirilir |
| **Xcode** | DerivedData, Simulators… | Sonraki build'de yeniden oluşur |

### Risk seviyelerine göre karar

| Gösterge | Anlam | Örnek |
| -------- | ----- | ----- |
| 🟢 Yeşil nokta / **safe** | Sonraki build/komutla yeniden oluşur | Homebrew cache, JetBrains cache, Cursor cache |
| 🟡 Sarı | Büyük yeniden indirme gerekir | Xcode Archives, Simulator cihazları |
| 🔴 Kırmızı | Geri dönüşü zor veri | Docker container verisi |

Hero alanındaki **XXX MB safe** yalnızca 🟢 güvenli önbelleklerin toplamını gösterir.

### Projects - proje artıkları

1. **Projects** sekmesine geç
2. ClearDisk şu klasörlerde eski proje artıklarını arar:

```
~/Documents   ~/Developer   ~/Projects   ~/Code   ~/Desktop
```

3. Bulunan artıklar listelenir - `node_modules`, `target/`, `.build/`, `build/`, `vendor/` vb. (11 proje tipi: Node.js, Rust, Swift, Go, Gradle, Maven, PHP, Ruby, Flutter, CMake)
4. Artık bulunamazsa **No stale project artifacts found** mesajı görünür; tarama yolları altında listelenir
5. Silmeden önce projenin hâlâ gerekli olup olmadığını kontrol et; temizlenen dosyalar **Çöp Kutusu'na** gider

> **Projects** sekmesi tam disk taraması yapmaz - yalnızca yukarıdaki standart geliştirici dizinlerine bakar. Projelerin başka bir yoldaysa (ör. `~/repos`) ClearDisk onları bu sekmede göstermez.

### Overview - disk dökümü ve trend

1. **Overview** sekmesine geç (gerekirse **Back** ile ana panele dön)
2. Sistem kategorilerini boyut çubuklarıyla gör:

| Kategori | Ne kapsar |
| -------- | --------- |
| Applications | Kurulu uygulamalar |
| Movies | Film / video dosyaları |
| Documents | Belge klasörü |
| Caches | Genel sistem önbellekleri |
| Photos / Music | Medya kütüphaneleri |
| Developer | Geliştirici dosyaları (küçük kalabilir - asıl büyük alan **Developer** sekmesinde) |
| Downloads / Desktop | İndirilenler ve masaüstü |

3. **Storage Trend** grafiği disk kullanım eğilimini gösterir; yeni kurulumda `0d history` veya `collecting data...` görünebilir - birkaç gün kullanım sonrası tahmin oluşur

> **Overview** genel disk fotoğrafıdır; geliştirici önbelleği temizliği için **Developer** sekmesini kullan.

### Large Files - büyük dosyalar

1. **Large Files** sekmesine geç
2. Kategoriler (ör. **Movies - 13 files - 14.5 GB**) chevron ile genişletilir
3. Büyük medya veya arşiv dosyalarını gözden geçir; silme ClearDisk'ten değil Finder'dan yapılır - bu sekme **keşif** içindir

### DerivedData proje dökümü

Xcode DerivedData listelendiğinde hangi uygulamanın ne kadar yer kapladığını proje adıyla gör; yalnızca belirli projeleri hedeflemek istersen satırdaki 🗑️ ile tek tek temizle.

### Menü çubuğu monitörü

| Disk doluluk | Davranış |
| ------------ | -------- |
| Normal | Standart renk, kullanım yüzdesi |
| ≥ %80 | Renk değişimi + bildirim |
| ≥ %90 | Kritik renk + temizlenebilir alan vurgusu |

---

## ⚠️ Bilinen Sorunlar ve Çözümleri

| Sorun | Neden Olur | Çözüm |
| ----- | ---------- | ----- |
| Uygulama açılmıyor / Gatekeeper engeli | Notarize edilmemiş | Sistem Ayarları → **Yine de Aç** veya `xattr -cr /Applications/ClearDisk.app` |
| Intel Mac'te çalışmıyor | Şu an yalnızca Apple Silicon | Intel desteği gelene kadar alternatif araçlar (DevCleaner, `brew cleanup`) |
| Xcode temizliği beklenmedik davranış | Xcode açıkken cache kilitli | Xcode'u kapat, ClearDisk uyarısını dikkate al |
| Docker verisi kayboldu | 🔴 Riskli Docker önbelleği temizlendi | Çöp Kutusu'ndan geri yükle; Docker temizliğinde risk etiketini oku |
| Temizlik sonrası yavaş build | DerivedData / paket cache silindi | Normal - ilk build yeniden indirir ve oluşturur |
| Forecast görünmüyor / `collecting data...` | Yeterli anlık görüntü yok | Birkaç gün normal kullan; paneli ara sıra aç - snapshot birikince tahmin oluşur |
| Overview'daki Developer çok küçük görünüyor | Farklı tarama kapsamı | Büyük geliştirici alanı **Developer** sekmesinde listelenir; Overview genel kategori özetidir |
| Clean Caches Large Files silmedi | Farklı işlev | **Clean Caches** yalnızca Developer önbelleklerini hedefler; büyük dosyalar Finder'dan yönetilir |
| OnyX / Mac Sai ile karışıklık | Farklı kapsam | ClearDisk = geliştirici önbellekleri; OnyX/Mac Sai = genel sistem bakımı |

---

## 🔗 Faydalı Bağlantılar

- 🌐 [Resmi Web Sitesi](https://bysiber.github.io/cleardisk/)
- 💾 [GitHub Sayfası](https://github.com/bysiber/cleardisk)
- 📦 [GitHub Releases](https://github.com/bysiber/cleardisk/releases/latest)
- 📖 [CHANGELOG](https://github.com/bysiber/cleardisk/blob/main/CHANGELOG.md)
- 🗣️ [GitHub Discussions](https://github.com/bysiber/cleardisk/discussions)
- 📦 [Homebrew Tap](https://github.com/bysiber/homebrew-cleardisk)
- 🍺 Kurulum: `brew tap bysiber/cleardisk && brew install --cask cleardisk`

---

## 📝 Notlar

> ClearDisk, geliştirici Mac'lerinde kayıp disk alanının büyük kısmını tek menü çubuğu aracında toplar. CleanMyMac veya DaisyDisk gibi ücretli genel temizleyicilerin yerine geçmez; **Xcode + Homebrew + npm + Docker + Cursor** ekosistemine odaklanır. Tipik aktif geliştiricide **50–200 GB** geri kazanım mümkündür. [Thaw](Thaw.md) ile menü çubuğunda gizleyip gerektiğinde açmak, kalabalığı azaltırken disk monitörünü el altında tutmanı sağlar.

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
