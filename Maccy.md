# 🛠️ Maccy

> **Kısa Açıklama:** macOS için hafif, açık kaynaklı ve klavye odaklı pano yöneticisi; kopyalama geçmişini hızlıca arayıp yeniden kullanmanı sağlar.

v2.6.1 · macOS 14+ (Apple Silicon / Intel) · MIT / açık kaynak · Pano yönetimi

---

## 📌 Genel Bakış

Maccy, macOS'un tek öğeli panosunun sınırlamasını giderir: kopyaladığın metinleri, bağlantıları ve kod parçalarını geçmişte tutar; arayıp saniyeler içinde geri çağırırsın. Paste, CopyClip veya Alfred pano özelliğine kıyasla bilinçli olarak sade tutulmuştur - gereksiz özellik yok, düşük bellek kullanımı ve yerel macOS arayüzü var. 1Password gibi parola yöneticilerinin panodan sildiği gizli içerikleri de otomatik yok sayar; veriler yalnızca bilgisayarında kalır.

---

## ✨ Öne Çıkan Özellikler

- **Hafif ve hızlı** - Tüm pano geçmişinde anında arama; arka planda minimum kaynak tüketimi
- **Klavye odaklı** - Fareye dokunmadan ara, seç, yapıştır; numaralı kısayollarla hızlı erişim
- **Güvenli ve gizli** - Gizli/geçici pano türlerini ve parola yöneticisi içeriklerini varsayılan olarak yok sayar
- **Yerel arayüz** - macOS'a uyumlu minimal menü çubuğu ve liste görünümü
- **Açık kaynak ve ücretsiz** - [MIT](https://github.com/p0deje/Maccy/blob/master/LICENSE) lisanslı; GitHub'dan denetlenebilir kaynak kod
- **Sabitleme (pin)** - Sık kullandığın öğeleri listenin üstüne sabitle; kalıcı kısayol atanır
- **Biçimli / biçimsiz yapıştırma** - `Option + Enter` ile doğrudan yapıştır; `Option + Shift + Enter` ile biçimlendirme olmadan
- **Geçici devre dışı bırakma** - Hassas kopyalama öncesi pano kaydını tek tıkla veya bir sonraki kopya için duraklat
- **Özelleştirilebilir kısayol** - Varsayılan `Shift + Cmd + C`; tercihlerden değiştirilebilir
- **Çoklu dil** - Weblate üzerinden Türkçe dahil yerelleştirme desteği

---

## 📥 İndirme ve Kurulum

### Yöntem 1: Homebrew (Önerilen)

```bash
brew install --cask maccy
```

> Homebrew yüklü değilse: [brew.sh](https://brew.sh) adresindeki komutu Terminal'de çalıştır.

### Yöntem 2: Resmi İndirme

1. [maccy.app](https://maccy.app/) adresine git
2. **Download now** ile en güncel sürümü indir veya [GitHub Releases](https://github.com/p0deje/Maccy/releases/latest) sayfasından `.zip` dosyasını al
3. `Maccy.app` dosyasını **Applications** klasörüne taşı
4. Gatekeeper uyarısı çıkarsa: Sistem Ayarları → Gizlilik ve Güvenlik → Yine de Aç

### Yöntem 3: App Store

[Maccy - App Store](https://apps.apple.com/app/maccy/id1527619437) üzerinden de kurulabilir; geliştiriciyi desteklemek isteyenler için alternatif.

---

## ⚙️ İlk Kurulum ve Önerilen Ayarlar

1. **Girişte başlat:** Menü çubuğundaki Maccy simgesi → **Preferences → General → Launch Maccy at login**
2. **Otomatik yapıştırma (isteğe bağlı):** **Preferences → General → Paste automatically** - seçince geçmişten öğe seçildiğinde doğrudan yapıştırır; **Erişilebilirlik** izni gerekir
3. **Erişilebilirlik izni (otomatik yapıştırma için):** Sistem Ayarları → Gizlilik ve Güvenlik → Erişilebilirlik → Maccy'i etkinleştir
4. **Geçmiş boyutu:** **Preferences → Storage → History size** - disk kullanımına göre öğe sayısını ayarla
5. **Evrensel Pano (Universal Clipboard) yok sayma (isteğe bağlı):** **Preferences → Ignore → Pasteboard Types** → `com.apple.is-remote-clipboard` ekle - iPhone/iPad'den gelen kopyaları geçmişe almaz
6. **Dil:** macOS sistem dilin Türkçe ise Maccy arayüzü de Türkçe görünür; değilse Weblate çevirileri uygulanır

> 💡 `Shift + Cmd + C` bazı uygulamalarda "biçimsiz kopyala" anlamına gelebilir. Çakışma yaşarsan **Preferences → General → Popup shortcut** ile farklı bir kombinasyon seç (ör. `Option + Cmd + V`).

---

## 🚀 Temel Kullanım

### Pano geçmişini açma ve arama

1. `Shift + Cmd + C` tuşlarına bas veya menü çubuğundaki Maccy simgesine tıkla
2. Açılan listede yazarak ara - eşleşen öğeler anında filtrelenir
3. `Enter` ile seçili öğeyi panoya kopyala; `Option + Enter` ile seç ve yapıştır
4. `Option + Shift + Enter` ile biçimlendirme olmadan yapıştır

### Sabitleme ve silme

- **Sabitle:** Öğe seçiliyken `Option + P` - listenin üstüne taşınır ve kalıcı numaralı kısayol alır
- **Tek öğe sil:** `Option + Delete`
- **Tüm sabitlenmemiş öğeleri temizle:** Menüden **Clear** veya `Option + Cmd + Delete`
- **Sabitlenenler dahil hepsini temizle:** Menüde **Clear**'a `Option` basılı tıkla veya `Shift + Option + Cmd + Delete`

### Hassas kopyalama

- **Maccy'yi geçici kapat:** Menü simgesine `Option` basılı tıkla - yeni kopyalar kaydedilmez
- **Yalnızca bir sonraki kopyayı yok say:** Menü simgesine `Option + Shift` basılı tıkla

### Klavye kısayolları

> Aşağıdaki kısayollar **varsayılan** değerlerdir; kendi ayarlarına, sabitlediğin öğelere veya macOS sürümüne göre farklı olabilir. Pano geçmişini açma tuşu **Preferences → General → Popup shortcut** ile değiştirilebilir; sabitlenen öğeler listenin üstüne taşınırken kalıcı numaralı kısayol alır.

| Kısayol | İşlev |
| ------- | ----- |
| `Shift + Cmd + C` | Pano geçmişini aç (varsayılan) |
| `Enter` | Seçili öğeyi panoya kopyala |
| `Option + Enter` | Seç ve yapıştır |
| `Option + Shift + Enter` | Seç ve biçimsiz yapıştır |
| `Cmd + n` | n. öğeyi seç (1–9) |
| `Option + n` | n. öğeyi seç ve yapıştır |
| `Option + P` | Öğeyi sabitle / sabitlemeyi kaldır |
| `Option + Delete` | Seçili öğeyi sil |
| `Option + Cmd + Delete` | Sabitlenmemiş tüm geçmişi temizle |
| `Cmd + ,` | Tercihler |

---

## ⚠️ Bilinen Sorunlar ve Çözümleri

| Sorun | Neden Olur | Çözüm |
| ----- | ---------- | ----- |
| Seçince yapıştırmıyor | Otomatik yapıştırma kapalı veya izin yok | Preferences → **Paste automatically** açık olsun; Sistem Ayarları → Erişilebilirlik → Maccy etkinleştir |
| Kısayol çalışmıyor | macOS'ta aynı kombinasyon kullanılıyor | Sistem Ayarları → Klavye → Klavye Kısayolları → çakışan kısayolu kapat; Maccy'yi yeniden başlat |
| Kısayol atarken "already used" uyarısı | Sistem hizmeti aynı tuşu kullanıyor | Klavye Kısayolları → Hizmetler → Metin gibi bölümlerde çakışmayı kaldır ([örnek](https://github.com/p0deje/Maccy/assets/576152/446719e6-c3e5-4eb0-95fb-5a811066487f)) |
| Parola alanında kısayol çalışmıyor | Kısayol yazdırılabilir karakter üretiyor (ör. `Option+C` → "ç") | Karabiner-Elements ile farklı kombinasyona eşle veya `Cmd + Shift + C` gibi güvenli bir kısayol seç |
| iPhone/iPad kopyaları geçmişi dolduruyor | Evrensel Pano kaydı açık | Preferences → Ignore → Pasteboard Types → `com.apple.is-remote-clipboard` ekle |
| Alt bilgi (footer) görünmüyor | Görünüm ayarında kapalı | Preferences → Appearance → footer'ı aç veya `defaults write org.p0deje.Maccy showFooter 1` |

---

## 🔗 Faydalı Bağlantılar

- 🌐 [Resmi Web Sitesi](https://maccy.app/)
- 💾 [GitHub Sayfası](https://github.com/p0deje/Maccy)
- 📖 [GitHub README / Kullanım Kılavuzu](https://github.com/p0deje/Maccy#usage)
- 🍎 [App Store](https://apps.apple.com/app/maccy/id1527619437)
- 🌍 [Çeviriler (Weblate)](https://hosted.weblate.org/engage/maccy/)
- 📦 [Homebrew Cask](https://formulae.brew.sh/cask/maccy)

---

## 📝 Notlar

> Maccy bilinçli olarak tek işe odaklanır: pano geçmişi. Raycast veya Alfred gibi launcher'ların pano özelliği zaten varsa Maccy gereksiz olabilir; ancak bağımsız, hafif ve tam kontrollü bir pano geçmişi isteyenler için en iyi seçeneklerden biridir. Paste gibi ücretli alternatiflere kıyasla tamamen ücretsiz ve açık kaynaklıdır. macOS 14 (Sonoma) ve üzeri gerektirir - daha eski sistemlerde desteklenmez.

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
