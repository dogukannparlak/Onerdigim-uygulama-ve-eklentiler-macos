# 🛠️ MiddleClick

> **Kısa Açıklama:** MacBook trackpad ve Magic Mouse'ta üç parmakla tıklama/dokunmayı orta fare tuşu (scroll wheel click) gibi çalıştıran hafif, açık kaynaklı bir yardımcı uygulama.

v3.2.0 · macOS (Apple Silicon / Intel) · GPL-3.0 / açık kaynak · Girdi / trackpad

---

## 📌 Genel Bakış

MacBook trackpad'inde fiziksel orta fare tuşu yoktur; bu yüzden tarayıcıda sekmeyi orta tıkla kapatmak, Safari'de bağlantıyı arka planda açmak veya Terminal'de seçili metni yapıştırmak gibi işlemler varsayılan olarak mümkün değildir. MiddleClick, trackpad veya Magic Mouse üzerinde **üç parmakla tıklama veya dokunmayı** sistem genelinde orta tık olarak yorumlar. Windows/Linux alışkanlığı olanlar veya orta tıka dayalı tarayıcı iş akışı kullananlar için küçük ama etkili bir tamamlayıcıdır; arka planda çalışır, menü çubuğunda minimal bir simge bırakır.

---

## ✨ Öne Çıkan Özellikler

- **Orta tık emülasyonu** - Üç parmak tıklama/dokunma ile scroll wheel click davranışı
- **Trackpad ve Magic Mouse** - MacBook dahili trackpad ve Magic Mouse desteği
- **Sistem geneli** - Tarayıcı, Terminal ve orta tık destekleyen tüm uygulamalarda çalışır
- **Hafif** - Küçük boyut, düşük kaynak kullanımı; arka planda sessizce çalışır
- **Özelleştirilebilir parmak sayısı** - 2–10 parmak arası `defaults` ile ayarlanabilir (varsayılan: 3)
- **Dokunma hassasiyeti** - Maksimum hareket ve süre eşikleri Terminal üzerinden ince ayar
- **Açık kaynak ve ücretsiz** - [GPL-3.0](https://github.com/artginzburg/MiddleClick/blob/main/LICENSE); kaynak kod denetlenebilir
- **Homebrew desteği** - Tek komutla kurulum ve güncelleme

---

## 📥 İndirme ve Kurulum

### Yöntem 1: Homebrew (Önerilen)

```bash
brew install --cask middleclick
```

> Homebrew yüklü değilse: [brew.sh](https://brew.sh) adresindeki komutu Terminal'de çalıştır.

### Yöntem 2: GitHub Releases

1. [GitHub Releases](https://github.com/artginzburg/MiddleClick/releases/latest) sayfasına git
2. En güncel sürümü indir
3. `MiddleClick.app` dosyasını **Applications** klasörüne taşı
4. Gatekeeper uyarısı çıkarsa: Sistem Ayarları → Gizlilik ve Güvenlik → Yine de Aç

> v1 veya v2 kullanıyorsan [Migration rehberi](https://github.com/artginzburg/MiddleClick/blob/main/docs/MIGRATIONS.md)ne bak.

---

## ⚙️ İlk Kurulum ve Önerilen Ayarlar

1. **Erişilebilirlik izni (zorunlu):** İlk açılışta macOS izin ister → Sistem Ayarları → Gizlilik ve Güvenlik → **Erişilebilirlik** → MiddleClick'i etkinleştir
2. **Girişte başlat:** MiddleClick'i bir kez aç; menü çubuğu simgesinden **Launch at login** (varsa) veya Sistem Ayarları → Genel → Giriş Öğeleri'ne ekle
3. **Trackpad ayarı:** Sistem Ayarları → Trackpad → **Tıklama yap** etkin olsun - üç parmak tıklama için gerekli
4. **Menü çubuğu simgesini gizle (isteğe bağlı):** `Cmd` basılı tutup simgeyi menü çubuğundan dışarı sürükle (✖️ görünene kadar); geri getirmek için çalışan MiddleClick'i tekrar aç

> 💡 macOS'ta **Üç Parmakla Sürükle** (Three Finger Drag) açıksa MiddleClick ile çakışabilir. Sorun yaşarsan [Three Finger Drag rehberine](https://github.com/artginzburg/MiddleClick/blob/main/docs/three-finger-drag.md) bak veya parmak sayısını 4'e çıkar.

### Gelişmiş ayarlar (`defaults`)

Parmak sayısı ve dokunma hassasiyeti Terminal'den değiştirilebilir. Değişiklikten sonra MiddleClick'i yeniden başlat.

```bash
# Parmak sayısı (varsayılan: 3)
defaults write art.ginzburg.MiddleClick fingers 4

# Tanımlanan sayıdan fazla parmakla da tetikle (varsayılan: false)
defaults write art.ginzburg.MiddleClick allowMoreFingers true

# Dokunmada izin verilen imleç hareketi (varsayılan: 0.05)
defaults write art.ginzburg.MiddleClick maxDistanceDelta 0.03

# Dokunma süresi üst sınırı, ms (varsayılan: 300)
defaults write art.ginzburg.MiddleClick maxTimeDelta 150
```

> ⚠️ `fingers` değerini **2** yapmak normal iki parmak sağ tık ve tek parmak tıklamayla çakışır; genelde önerilmez.

---

## 🚀 Temel Kullanım

### Orta tık hareketi

1. MiddleClick çalışır durumda olsun (menü çubuğunda simge veya gizli arka plan)
2. Trackpad veya Magic Mouse üzerinde **üç parmakla tıkla** veya **üç parmakla dokun**
3. Sistem, bunu orta fare tuşu tıklaması olarak iletir

### Yaygın kullanım senaryoları

| Senaryo | Davranış |
| ------- | -------- |
| **Tarayıcı sekmesi** | Sekmeye orta tık → sekmeyi kapat |
| **Safari bağlantısı** | Bağlantıya orta tık → arka planda yeni sekme aç |
| **Terminal** | Seçili metne orta tık → yapıştır |
| **Genel** | Orta tık destekleyen her uygulamada aynı mantık |

> MiddleClick yalnızca orta tık **emülasyonu** yapar; `Cmd + tık` gibi macOS kısayollarının yerine geçmez.

---

## ⚠️ Bilinen Sorunlar ve Çözümleri

| Sorun | Neden Olur | Çözüm |
| ----- | ---------- | ----- |
| Orta tık hiç çalışmıyor | Erişilebilirlik izni yok | Sistem Ayarları → Erişilebilirlik → MiddleClick açık olsun; uygulamayı yeniden başlat |
| Güncelleme sonrası izin bozuldu | macOS güncellenmiş binary'yi farklı uygulama sayar | MiddleClick'i kapat → Erişilebilirlik listesinden kaldır → Uygulamayı açıp izni yeniden ver |
| Üç parmak hareketi tutarsız | Three Finger Drag veya trackpad ayarı çakışması | [Three Finger Drag rehberi](https://github.com/artginzburg/MiddleClick/blob/main/docs/three-finger-drag.md); veya `fingers 4` dene |
| Antivirus / CleanMyMac uyarısı | Erişilebilirlik ve multitouch API kullanımı | Yanlış pozitif; kaynak kodu denetlenebilir. Vendor'a false positive bildir |
| Yanlışlıkla orta tık tetikleniyor | Avuç içi veya ek parmak dokunuşu | `allowMoreFingers false` bırak; `maxDistanceDelta` ve `maxTimeDelta` değerlerini sıkılaştır |

---

## 🔗 Faydalı Bağlantılar

- 💾 [GitHub Sayfası](https://github.com/artginzburg/MiddleClick)
- 📦 [GitHub Releases](https://github.com/artginzburg/MiddleClick/releases/latest)
- 📖 [Sorun giderme](https://github.com/artginzburg/MiddleClick/blob/main/docs/troubleshooting.md)
- 📖 [Three Finger Drag çakışması](https://github.com/artginzburg/MiddleClick/blob/main/docs/three-finger-drag.md)
- 📖 [v1/v2 geçiş rehberi](https://github.com/artginzburg/MiddleClick/blob/main/docs/MIGRATIONS.md)
- 📦 [Homebrew Cask](https://formulae.brew.sh/cask/middleclick)

---

## 📝 Notlar

> MiddleClick tek işe odaklanır: trackpad/Magic Mouse'ta orta tık. Harici fare kullananlarda zaten fiziksel orta tuş vardır; bu uygulama özellikle MacBook trackpad kullananlar için anlamlıdır. Tamamen ücretsiz ve açık kaynaklıdır; geliştiriciyi desteklemek istersen GitHub Sponsors veya README'deki bağış adreslerine bakabilirsin.

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
