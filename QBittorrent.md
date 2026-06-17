# 🛠️ qBittorrent

> **Kısa Açıklama:** Reklamsız, açık kaynak BitTorrent istemcisi; torrent ve magnet linkleriyle dosya indirmeni sağlar.

Güncel · macOS (Apple Silicon / Intel) · Ücretsiz / açık kaynak · İndirme

---

## 📌 Genel Bakış

qBittorrent, dosyaları merkezi sunucudan değil diğer kullanıcılardan (P2P) parçalar halinde indiren BitTorrent protokolünü kullanan bir istemcidir. `.torrent` dosyası veya magnet link ile indirme başlatılır. µTorrent'e reklamsız alternatif olarak bilinir; Web arayüzü, arama ve RSS desteği sunar.

---

## ✨ Öne Çıkan Özellikler

- **Reklamsız ve ücretsiz** - Spyware veya gizli yazılım yok
- **Magnet desteği** - Link yapıştırarak hızlı indirme
- **RSS otomasyonu** - Kurallara göre otomatik indirme
- **macOS uyumlu** - Apple Silicon ve Intel Mac desteği

---

## 📥 İndirme ve Kurulum

### Yöntem 1: Homebrew (Önerilen)

```bash
brew install --cask qbittorrent
```

> Homebrew yüklü değilse: [brew.sh](https://brew.sh) adresindeki komutu Terminal'de çalıştır.

### Yöntem 2: Resmi İndirme

1. [qbittorrent.org/download](https://www.qbittorrent.org/download) adresine git
2. macOS sürümünü indir (.dmg)
3. Uygulamayı **Applications** klasörüne sürükle
4. Gatekeeper uyarısı çıkarsa aşağıdaki **"Resmi uygulama değil" uyarısı** bölümüne bak

### "Resmi uygulama değil" uyarısı

macOS ilk açılışta *"qBittorrent açılamıyor çünkü geliştirici doğrulanamıyor"* veya benzeri bir uyarı gösterebilir. Uygulama resmi kaynaktan indirilmiş olsa bile Gatekeeper bunu engelleyebilir. Şu adımlarla ayarlardan izin ver:

1. Uyarıyı **Tamam** ile kapat (pencereyi kapatma; uygulama açılmaz)
2. **Sistem Ayarları** → **Gizlilik ve Güvenlik**'i aç
3. Aşağı kaydır; **Güvenlik** bölümünde *"qBittorrent" engellendi* benzeri bir satır görünür
4. **Yine de Aç** (veya **Aç**) düğmesine tıkla
5. Onay penceresinde tekrar **Aç** de

> **Alternatif (ilk kez):** Finder'da **Applications** → qBittorrent'e **sağ tık** → **Aç** → açılan uyarıda **Aç**. Sonraki açılışlarda normal çift tık yeterli olur.

> Uyarı hiç görünmüyorsa uygulamayı bir kez açmayı dene; macOS engellediğinde **Gizlilik ve Güvenlik** sayfasına ilgili seçenek eklenir.

---

## ⚙️ İlk Kurulum ve Önerilen Ayarlar

1. **Dil:** Araçlar → Seçenekler → Davranış → Arayüz dili → **Türkçe**
2. **İndirme klasörü:** Araçlar → Seçenekler → İndirmeler → Varsayılan kayıt yolu

> 💡 İndirme tamamlandıktan sonra paylaşım (seeding) devam eder; bant genişliğini tüketmemesi için hız limiti veya otomatik durdurma ayarla.

---

## 🚀 Temel Kullanım

### Torrent ekleme

1. `.torrent` dosyasını qBittorrent penceresine **sürükle-bırak**
2. Veya **Cmd + O** → torrent dosyasını seç
3. İndirme konumunu onayla → **Tamam**

### Magnet link ekleme

1. Magnet linkini kopyala
2. **Cmd + Shift + O** → linki yapıştır
3. Veya qBittorrent açıkken **Cmd + V** (pano otomatik algılanır)

### Klavye kısayolları


| Kısayol            | İşlev                   |
| ------------------ | ----------------------- |
| `Cmd + O`         | Torrent dosyası ekle    |
| `Cmd + Shift + O` | Magnet / URL ekle       |
| `Cmd + P`         | Duraklat / devam et     |
| `Delete`           | Seçili torrent'i kaldır |
| `F3`               | RSS okuyucu             |


---

## ⚠️ Bilinen Sorunlar ve Çözümleri


| Sorun                      | Neden Olur              | Çözüm                                                      |
| -------------------------- | ----------------------- | ---------------------------------------------------------- |
| "Resmi uygulama değil" / açılmıyor | macOS Gatekeeper engeli | Sistem Ayarları → Gizlilik ve Güvenlik → **Yine de Aç**; veya sağ tık → Aç |
| İndirme yavaş              | Az seeder / port kapalı | UPnP açık mı kontrol et; farklı torrent dene               |
| Metadata bekliyor          | Magnet henüz eşleşmedi  | Birkaç dakika bekle; DHT etkin olsun                       |
| Port kapalı (turuncu ikon) | Router / firewall       | Araçlar → Seçenekler → Bağlantı → UPnP/NAT-PMP etkinleştir |
| Dosya bulunamıyor          | Taşınmış veya silinmiş  | Sağ tık → Konumu belirt                                    |
| Disk dolu                  | Hedef sürücü dolu       | İndirme klasörünü değiştir veya yer aç                     |


---

## 🔗 Faydalı Bağlantılar

- 🌐 [Resmi Web Sitesi](https://www.qbittorrent.org/)
- 💾 [GitHub Sayfası](https://github.com/qbittorrent/qBittorrent)
- 📖 [Wiki / SSS](https://github.com/qbittorrent/qBittorrent/wiki)
- 📦 [Homebrew Cask](https://formulae.brew.sh/cask/qbittorrent)

---

## 📝 Notlar

> BitTorrent yasal içerikler (Linux ISO, açık kaynak yazılımlar vb.) için kullanılabilir; telif hakkı ihlali yasal sorumluluk doğurur. P2P ağında IP adresin görünür - VPN kullanımı gizlilik tercihinize bağlıdır. Yalnızca güvendiğin kaynaklardan torrent indir.

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
