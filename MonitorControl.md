# 🛠️ MonitorControl

> **Kısa Açıklama:** Harici monitörlerin parlaklık, ses ve kontrastını Mac klavye tuşları veya menü çubuğu kaydırıcılarıyla yerleşik Apple ekranı gibi kontrol eden ücretsiz, açık kaynaklı bir ekran yönetim aracı.

v4.3.3 · macOS 10.15+ (Apple Silicon / Intel) · MIT / açık kaynak · Ekran yönetimi

---

## 📌 Genel Bakış

Harici monitör bağladığında macOS genelde parlaklık tuşlarını (`F1` / `F2`) yalnızca dahili ekrana yönlendirir; harici ekranın fiziksel düğmelerine ulaşmak zorunda kalırsın. MonitorControl bu boşluğu doldurur: DDC/CI protokolüyle donanım parlaklığı, Apple protokolüyle yerleşik ekranlar, gamma/shade ile yazılımsal karartma sunar ve yerel macOS OSD'sini gösterir. [BetterDisplay](BetterDisplay.md) ile aynı geliştirici ekosisteminden gelir; MonitorControl daha hafif ve odaklıdır - yalnızca parlaklık, ses ve kontrast kontrolü istersen ideal seçimdir.

---

## ✨ Öne Çıkan Özellikler

- **Parlaklık, ses ve kontrast** - Harici monitörleri klavye veya menü kaydırıcılarıyla kontrol et
- **Yerel macOS OSD** - Apple ekranlarındaki gibi parlaklık/ses göstergesi (Tahoe'de yüzde değeri sınırlı)
- **Çoklu protokol** - DDC (harici), Apple native (dahili/Apple Display), gamma tablosu, shade (DisplayLink/AirPlay/Sidecar)
- **Donanım + yazılım karartma** - Minimum parlaklığın altına inme; tam siyaha kadar karartma
- **Ekran senkronizasyonu** - Tüm ekranları tek kaydırıcı veya kısayolla eşitle; dahili ekran parlaklığını harici ekrana yansıt
- **Apple klavye tuşları** - `F1`/`F2` ve medya tuşlarını harici monitöre yönlendir (Erişilebilirlik izni gerekir)
- **Özel klavye kısayolları** - Settings → Keyboard altında tamamen özelleştirilebilir
- **Gelişmiş ayarlar** - Donanımına göre ince ayar için **Show advanced settings** seçeneği
- **Tamamen ücretsiz** - Açık kaynak ([MIT](https://github.com/MonitorControl/MonitorControl/blob/main/License.txt)); abonelik veya Pro sürüm yok

---

## 📥 İndirme ve Kurulum

### Yöntem 1: Homebrew (Önerilen)

```bash
brew install --cask monitorcontrol
```

> Homebrew yüklü değilse: [brew.sh](https://brew.sh) adresindeki komutu Terminal'de çalıştır.

### Yöntem 2: GitHub Releases

1. [GitHub Releases](https://github.com/MonitorControl/MonitorControl/releases/latest) sayfasına git
2. En güncel `.dmg` dosyasını indir
3. `MonitorControl.app` dosyasını **Applications** klasörüne taşı
4. Gatekeeper uyarısı çıkarsa: Sistem Ayarları → Gizlilik ve Güvenlik → Yine de Aç

> ⚠️ **v4.2.0** macOS Sequoia/Tahoe'de bazı yapılandırmalarda çökebilir ve otomatik güncellenmez. **v4.3.3 veya üzeri** kullan.

**macOS uyumluluğu:**

| MonitorControl | macOS |
| -------------- | ----- |
| v4.3.3+ | Sequoia, Tahoe 26 *(gerekli)* |
| v4.0.0 | Catalina 10.15+ *(Big Sur+ tam işlev)* |
| v3.1.1 | Mojave 10.14 |
| v2.1.0 | Sierra 10.12 |

---

## ⚙️ İlk Kurulum ve Önerilen Ayarlar

1. **Uygulamayı aç:** Menü çubuğunda parlaklık simgesi görünür
2. **Erişilebilirlik izni (klavye tuşları için):** Yerleşik `F1`/`F2` ve medya tuşlarını kullanacaksan → Sistem Ayarları → Gizlilik ve Güvenlik → **Erişilebilirlik** → MonitorControl'i etkinleştir. Yalnızca menü kaydırıcıları yeterliyse atlayabilirsin
3. **Girişte başlat:** Settings → **General** → **Launch at login**
4. **Gelişmiş ayarlar:** Settings → **Show advanced settings** - DDC, gamma, senkronizasyon ve donanımına özel seçenekler
5. **Klavye:** Settings → **Keyboard** - Apple medya tuşlarını varsayılan kullanır; istersen özel kısayol tanımla
6. **BetterDisplay çakışması:** İki uygulama da DDC kullanıyorsa birinde DDC'yi kapat veya yalnızca birini aktif tut ([BetterDisplay.md](BetterDisplay.md))

> 💡 Sequoia/Tahoe için **v4.3.3+** şart. Tahoe'da Control Center OSD görünür ancak yüzde değeri güncellenmeyebilir - bilinen sınırlama.

---

## 🚀 Temel Kullanım

### Menü çubuğu kaydırıcıları

1. Menü çubuğundaki MonitorControl simgesine tıkla
2. Her bağlı ekran için parlaklık (ve destekleniyorsa ses/kontrast) kaydırıcısını kullan
3. **Sync** etkinse tek kaydırıcı tüm ekranları birlikte ayarlar

### Klavye ile kontrol

1. Erişilebilirlik izni verilmiş olsun
2. `F1` / `F2` ile parlaklığı ayarla (imlecin bulunduğu veya odaklı ekrana göre)
3. Özel kısayollar için **Settings → Keyboard** bölümünü kullan

> Aşağıdaki kısayollar **varsayılan** davranıştır; **Settings → Keyboard** altından değiştirilebilir veya devre dışı bırakılabilir.

| Kısayol | İşlev |
| ------- | ----- |
| `F1` / `F2` | Parlaklık azalt / artır (Apple klavye, izin gerekir) |
| Medya tuşları | Ses kontrolü (desteklenen monitörlerde) |
| *(özelleştirilebilir)* | Settings → Keyboard'dan atanır |

### Donanım vs yazılım karartma

- **DDC destekli monitör** (USB-C, DisplayPort vb.): Donanım arka ışığı doğrudan kontrol edilir - tercih edilen yöntem
- **DDC desteklemeyen TV / DisplayLink / Sidecar:** Yazılımsal shade (overlay) veya gamma ile karartma
- **Kombine mod:** Donanım minimuma indikten sonra yazılımsal karartmayla tam siyaha inme

---

## ⚠️ Bilinen Sorunlar ve Çözümleri

| Sorun | Neden Olur | Çözüm |
| ----- | ---------- | ----- |
| Harici monitör parlaklığı değişmiyor | DDC desteklenmiyor veya hub/dongle | Doğrudan Mac portuna bağla (USB-C/DP); Settings → advanced → DDC seçeneklerini dene |
| M1/M2 Mac mini HDMI DDC çalışmıyor | Apple Silicon dahili HDMI DDC desteklemiyor | USB-C ile bağla veya [BetterDisplay](BetterDisplay.md) ile HDMI DDC |
| DisplayLink dock üzerinden DDC yok | Mac'te DisplayLink DDC iletmiyor | Yalnızca yazılımsal karartma mümkün |
| Klavye tuşları çalışmıyor | Erişilebilirlik izni yok | Sistem Ayarları → Erişilebilirlik → MonitorControl açık olsun |
| v4.2.0 çöküyor (Sequoia/Tahoe) | Bilinen sürüm hatası | **v4.3.3+**'a manuel güncelle |
| OSD yüzdesi görünmüyor (Tahoe) | macOS Tahoe sınırlaması | Bilinen sınırlama; kaydırıcı ve klavye yine çalışır |
| BetterDisplay ile çakışma | İki uygulama aynı DDC kanalını kullanıyor | Bir uygulamada DDC'yi kapat |
| EIZO vb. monitörlerde DDC yok | Özel protokol (MCCS/USB) | Yalnızca yazılımsal karartma |

---

## 🔗 Faydalı Bağlantılar

- 🌐 [Resmi Web Sitesi](https://monitorcontrol.app/)
- 💾 [GitHub Sayfası](https://github.com/MonitorControl/MonitorControl)
- 📦 [GitHub Releases](https://github.com/MonitorControl/MonitorControl/releases/latest)
- 🗣️ [GitHub Discussions](https://github.com/MonitorControl/MonitorControl/discussions)
- 📖 [GitHub Wiki](https://github.com/MonitorControl/MonitorControl/wiki)
- 📦 [Homebrew Cask](https://formulae.brew.sh/cask/monitorcontrol)
- 🖥 [BetterDisplay (gelişmiş alternatif)](BetterDisplay.md)

---

## 📝 Notlar

> MonitorControl, harici monitör parlaklığı ve ses kontrolü için en pratik ücretsiz çözümlerden biridir. XDR/HDR upscaling, esnek HiDPI, sanal ekran veya EDID override gibi gelişmiş ihtiyaçların varsa aynı ekosistemdeki [BetterDisplay](BetterDisplay.md) daha kapsamlıdır - ikisini birlikte kurabilirsin ama DDC çakışmasına dikkat et. Geliştirici [@waydabber](https://github.com/waydabber) her iki projeyi de sürdürüyor.

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
