# 🛠️ Applite

> **Kısa Açıklama:** Homebrew Cask uygulamalarını tek tıkla kurman, güncellemen ve kaldırman için sade bir arayüz sunan açık kaynaklı macOS uygulama yöneticisi.

v1.3.1 · macOS 13+ (Apple Silicon / Intel) · MIT / açık kaynak · Sistem / Paket yönetimi

---

## 📌 Genel Bakış

Applite, [Homebrew Cask](https://github.com/Homebrew/homebrew-cask) kataloğundaki üçüncü taraf uygulamaları Terminal komutları olmadan yönetmeni sağlar. Keşfet sayfasından kategorilere göz atabilir, arama ile uygulama bulabilir ve kurulum, güncelleme veya kaldırmayı tek tıkla yapabilirsin. Terminal'e alışkın olmayan kullanıcılar için Homebrew'un gücünü App Store benzeri bir arayüze taşır; mevcut Homebrew kurulumunla da uyumlu çalışır.

Homebrew henüz kurulu değilse veya temel komutları öğrenmek istiyorsan önce **[Homebrew.md](Homebrew.md)** rehberine bak.

---

## ✨ Öne Çıkan Özellikler

- **Tek tıkla kur / güncelle / kaldır** — Homebrew Cask uygulamalarını grafik arayüzden yönet
- **Keşfet galerisi** — Kategorilere ayrılmış, seçilmiş uygulama kataloğu
- **Bulanık arama** — Homebrew kataloğundaki tüm cask'leri hızlıca bul
- **Mevcut Homebrew ile uyum** — Var olan `brew` kurulumunu kullanabilir veya Applite'a özel ayrı bir kurulum oluşturabilirsin
- **Güncelleme denetimi** — Yüklü cask'ler için güncelleme bildirimi; "greedy" güncelleme davranışı ayarlanabilir
- **Ayna (mirror) indirme** — Yavaş veya kısıtlı ağlarda alternatif indirme kaynakları (ayarlardan yapılandırılır)
- **Sistem proxy desteği** — HTTP, HTTPS ve SOCKS5 proxy ayarlarını kullanır
- **Gizlilik** — Telemetri yok, izleme yok
- **Açık kaynak** — MIT lisanslı; [GitHub](https://github.com/milanvarady/Applite) üzerinden denetlenebilir

---

## 📥 İndirme ve Kurulum

### Yöntem 1: Homebrew (Önerilen)

```bash
brew install --cask applite
```

> Homebrew yüklü değilse: [Homebrew.md](Homebrew.md) rehberindeki kurulum adımlarını izle.

### Yöntem 2: Resmi İndirme

1. [aerolite.dev/applite](https://aerolite.dev/applite) veya [GitHub Releases](https://github.com/milanvarady/Applite/releases/latest) sayfasına git
2. **Applite.dmg** dosyasını indir
3. Uygulamayı **Applications** klasörüne sürükle
4. Gatekeeper uyarısı çıkarsa: Sistem Ayarları → Gizlilik ve Güvenlik → Yine de Aç

---

## ⚙️ İlk Kurulum ve Önerilen Ayarlar

1. **Homebrew seçimi:** İlk açılışta **Use existing brew** (mevcut kurulumu kullan) veya **Create new installation** (Applite'a özel kurulum) seç — mevcut cask'lerini görmek istiyorsan ilkini seç
2. **Katalog yenileme sıklığı:** Ayarlar → App Catalog fetch frequency — ilk yükleme yavaşsa sıklığı artır
3. **Greedy güncelleme:** Ayarlar → Greedy upgrade checking — uygulama içi güncellemeleri de kontrol etmek istiyorsan aç
4. **Ayna indirme (isteğe bağlı):** Ayarlar → Mirror Downloads — ağ erişimi kısıtlıysa etkinleştir
5. **Applite güncellemeleri:** Uygulama Sparkle ile kendi güncellemelerini bildirir

> 💡 Applite yalnızca **Homebrew Cask** ile kurulan uygulamaları yönetir. App Store veya `.dmg` ile manuel kurulan uygulamalar listede görünmez; yönetmek için Applite üzerinden yeniden kurman gerekir.

---

## 🚀 Temel Kullanım

### Uygulama kurma

1. Applite'ı aç
2. **Discover** sekmesinden kategorilere göz at veya arama çubuğuna uygulama adını yaz
3. Uygulama kartına tıkla → **Install**
4. Gerekirse yönetici parolasını gir

### Güncelleme

1. Sol menüden **Updates** (Güncellemeler) sekmesine geç
2. Güncellenebilir uygulamalar listelenir
3. Tek tek veya toplu **Update** ile güncelle

### Kaldırma

1. **Installed** (Yüklü) sekmesinden uygulamayı bul
2. **Uninstall** ile kaldır — arka planda `brew uninstall --cask` çalışır

### Homebrew token vs görünen ad

Uygulama adına tıklayarak görünen ad ile Homebrew token'ı (ör. `visual-studio-code`) arasında geçiş yapabilirsin.

### Klavye kısayolları

Applite fare odaklı bir arayüzdür; temel gezinme arama ve tıklama ile yapılır:

| Kısayol | İşlev |
| ------- | ----- |
| `Cmd + ,` | Ayarlar |
| `Cmd + F` | Arama (pencere içi) |
| `Cmd + Q` | Applite'dan çık |

---

## ⚠️ Bilinen Sorunlar ve Çözümleri

| Sorun | Neden Olur | Çözüm |
| ----- | ---------- | ----- |
| Kurulu uygulama listede yok | Homebrew dışından kurulmuş (App Store, DMG) | Applite üzerinden aynı cask'i kur; mevcut kurulumu tanır |
| İlk açılış yavaş | Katalog indiriliyor | Ayarlar → katalog yenileme sıklığını ayarla; sabırla bekle |
| Yönetici parolası isteniyor | Bazı cask'ler sistem düzeyinde kurulum gerektirir | Normal davranış; parolayı güvenli ortamda gir |
| App Store uygulamaları görünmüyor | Applite yalnızca Cask yönetir | App Store uygulamaları için Mac App Store'u kullan |
| İndirme başarısız | Ağ veya Homebrew kaynağı sorunu | Ayarlar → Mirror Downloads dene; `brew update` ile Terminal'den kontrol et |
| macOS 12 ve altında çalışmıyor | Minimum sürüm macOS 13 | Ventura veya üzeri gerekir |

---

## 🔗 Faydalı Bağlantılar

- 🌐 [Resmi Web Sitesi](https://aerolite.dev/applite)
- ❓ [SSS / FAQ](https://aerolite.dev/applite/FAQ.html)
- 💾 [GitHub Sayfası](https://github.com/milanvarady/Applite)
- 📖 [Katkı Rehberi](https://github.com/milanvarady/Applite/blob/main/docs/CONTRIBUTING.md)
- 🗺️ [Yol Haritası](https://github.com/users/milanvarady/projects/1)
- 💬 [Discord Sunucusu](https://discord.gg/MpDMH9cPbK)
- 📦 [Homebrew Cask](https://formulae.brew.sh/cask/applite)
- 🍺 [Homebrew Cask Kataloğu](https://formulae.brew.sh/cask/)
- 🍺 [Homebrew Rehberi (bu repo)](Homebrew.md)

---

## 📝 Notlar

> Applite, Homebrew'un GUI katmanıdır; tam bir uygulama mağazası değil. Yalnızca [Homebrew Cask kataloğunda](https://formulae.brew.sh/cask/) bulunan uygulamaları kurabilirsin. AppCleaner gibi kalıntı temizliği yapmaz — kaldırma işlemi `brew uninstall --cask` ile sınırlıdır. Bu repodaki diğer uygulama rehberlerindeki `brew install --cask` komutlarını Applite üzerinden de çalıştırabilirsin. Bağımsız geliştirici projesi olduğu için güncellemeler dönemsel gelir; açık kaynak olduğu için topluluk katkısına açıktır.

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
