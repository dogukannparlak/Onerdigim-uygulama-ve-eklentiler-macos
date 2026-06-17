# 🛠️ Mac Sai

> **Kısa Açıklama:** Mac'te gereksiz dosyaları temizleyen, kötü amaçlı yazılım tarayan, uygulamaları tam kaldıran ve disk kullanımını görselleştiren ücretsiz, açık kaynaklı sistem bakım aracı — CleanMyMac'e aboneliksiz alternatif.

v1.11.7 · macOS 14 Sonoma+ (Apple Silicon / Intel) · BSD-3-Clause / açık kaynak · Sistem / Bakım

---

## 📌 Genel Bakış

Mac Sai, tek arayüzden temizlik, güvenlik, performans ve dosya yönetimi sunan **ücretsiz ve açık kaynaklı** bir macOS yardımcı programıdır. CleanMyMac'in başlıca işlevlerini (Smart Scan, sistem çöpü, kötü amaçlı yazılım taraması, tam kaldırma, disk görselleştirme vb.) abonelik ve telemetri olmadan hedefler. Swift 6 ve SwiftUI ile yazılmıştır; Apple tarafından **notarize** edilmiştir.

Eski adı **Mac Clean** idi (ticari marka nedeniyle Mac Sai olarak yeniden adlandırıldı). GitHub ve Homebrew bağlantıları güncellendi.

> **Abonelik yok. Telemetri yok. Reklam yok.**

---

## ✨ Öne Çıkan Özellikler

### Temizlik

- **Smart Scan** — Tek tıkla 13 modülü tarar; temizlik, koruma ve performans analizini birleştirir
- **System Junk** — 16 kategori: önbellek, log, dil dosyaları, bozuk tercihler, iOS yedekleri, Xcode artıkları, **Universal Binary inceltme** (arm64+x86_64 birleşik ikili dosyaları yalnızca native mimarine indirir) ve daha fazlası
- **Mail Attachments** — Apple Mail, Outlook ve Spark ek önbelleklerini bulur
- **Trash Bins** — Harici sürücüler dahil tüm çöp kutularını boşaltır

### Koruma

- **Malware Removal** — İmza tabanlı tarama; Quick / Balanced / Deep derinlikleri; launch agent, tarayıcı eklentisi ve bilinen kalıplar
- **Privacy** — Safari, Chrome ve Firefox geçmişi, çerez ve önbellek temizliği; sistem izleri için zaman filtresi

### Performans

- **Optimization** — Giriş öğeleri ve launch agent'ları aç/kapat
- **Maintenance** — 10 bakım görevi: RAM boşaltma, bakım scriptleri, izin onarımı, Launch Services yeniden oluşturma, Spotlight yeniden indeksleme, DNS flush, Time Machine snapshot inceltme. Görevler güvenli / yıkıcı olarak etiketlenir; **Run All** onay ister

### Uygulamalar

- **Uninstaller** — 10 seviyeli eşleştirme motoru; 17+ Library alt klasöründe ilişkili dosyaları bulur; tam kaldırma, uygulama sıfırlama, kullanılmayan uygulama tespiti
- **Updater** — Sparkle appcast ile kurulu uygulamalarda güncelleme kontrolü

### Dosyalar

- **Space Lens** — Disk kullanımını treemap ile görselleştir; drill-down gezinme
- **Large & Old Files** — 50 MB üzeri dosyaları boyut ve son erişim tarihine göre listele
- **Duplicates** — Aşamalı kopya bulucu (boyut → kısmi hash → tam hash → inode)
- **Shredder** — Güvenli silme (standart, kalıcı, üzerine yazma modları)

### Menü çubuğu widget'ı

- CPU, bellek, disk ve pil için canlı halka göstergeleri
- Ağ hızı, uptime, swap kullanımı
- Öneriler ("Kullanıcı önbelleği 2.5 GB'a ulaştı — System Junk çalıştır")
- Son kötü amaçlı yazılım taraması durumu
- Harici diskler ve monitörler
- İsteğe bağlı düşük disk / yüksek bellek uyarıları

---

## 📥 İndirme ve Kurulum

### Yöntem 1: Homebrew (Önerilen)

Mac Sai resmi Homebrew core'da değil; geliştirici tap'ı gerekir:

```bash
brew tap iliyami/macsai
brew install --cask mac-sai
```

> Homebrew yüklü değilse: [brew.sh](https://brew.sh) adresindeki komutu Terminal'de çalıştır.

**Eski Mac Clean kurulumundan geçiş:**

```bash
brew uninstall --cask mac-clean && brew untap iliyami/macclean
brew tap iliyami/macsai && brew install --cask mac-sai
```

Uygulama Apple tarafından notarize edildiği için Gatekeeper uyarısı olmadan açılır.

### Yöntem 2: Resmi İndirme

1. [GitHub Releases](https://github.com/iliyami/MacSai/releases/latest) sayfasından güncel `.dmg` indir
2. `Mac Sai.app` dosyasını **Applications** klasörüne sürükle

### Yöntem 3: Tek satır kurulum

```bash
curl -fsSL https://raw.githubusercontent.com/iliyami/MacSai/main/scripts/install.sh | bash
```

---

## ⚙️ İlk Kurulum ve Önerilen Ayarlar

1. **Tam Disk Erişimi (bazı modüller için):** Mail Attachments, Privacy ve Malware modülleri korumalı alanları tarayabilmek için **Sistem Ayarları → Gizlilik ve Güvenlik → Tam Disk Erişimi** → **+** ile Applications'tan **Mac Sai** ekle → uygulamayı yeniden başlat
2. **İlk Smart Scan:** Ana ekrandan **Smart Scan** çalıştır — temizlik, koruma ve performans özetini tek seferde gör
3. **Dry-run / önizleme:** İlk temizlikte ne silineceğini incele; silme varsayılan olarak **Çöp Kutusu'na** gider (geri alınabilir)
4. **Menü çubuğu widget'ı:** Kenar çubuğundan etkinleştir — CPU, bellek ve disk durumunu hızlıca izle
5. **Maintenance görevleri:** **Run All** kullanmadan önce yıkıcı (disruptive) etiketli görevleri oku; Spotlight yeniden indeksleme gibi işlemler geçici yavaşlamaya neden olabilir

> 💡 Tam kaldırma için [AppCleaner](AppCleaner.md) hâlâ hafif ve odaklı bir alternatiftir; Mac Sai daha geniş bir paket sunar (malware, bakım, Space Lens, duplicate finder). Güncelleme takibi için [Latest](Latest.md) ile birlikte kullanılabilir — Mac Sai'nin kendi Updater modülü Sparkle tabanlı uygulamaları kontrol eder.

---

## 🚀 Temel Kullanım

### Smart Scan (tek tık)

1. Mac Sai'yi aç
2. **Smart Scan** → tarama başlar; 13 modül canlı ilerleme gösterir
3. Sonuçları incele — temizlik, koruma ve performans önerileri listelenir
4. Onayladığın öğeleri temizle veya modül modül ilerle

### System Junk temizliği

1. Kenar çubuğundan **System Junk** seç
2. **Scan** → 16 kategoride bulunan dosyalar listelenir
3. Silmek istemediğin kategorilerin işaretini kaldır
4. **Clean** — dosyalar varsayılan olarak Çöp Kutusu'na gider

### Kötü amaçlı yazılım taraması

1. **Malware Removal** modülünü aç
2. Derinlik seç: **Quick**, **Balanced** veya **Deep**
3. Tarama tamamlanınca bulunan tehditleri incele ve kaldır

### Uygulama kaldırma

1. **Uninstaller** modülüne git
2. Kaldırmak istediğin uygulamayı seç
3. 10 seviyeli motor ilişkili tüm dosyaları listeler
4. **Uninstall** veya **Reset** (uygulama ayarlarını sıfırla, uygulamayı bırak)

### Disk analizi (Space Lens)

1. **Space Lens** → tarama başlat
2. Treemap'te en büyük alanları gör
3. Bloklara tıklayarak alt klasörlere in
4. Gereksiz büyük dosyaları Shredder veya Finder üzerinden yönet

### Bakım görevleri

1. **Maintenance** sekmesine git
2. Tek tek güvenli görevleri çalıştır veya **Run All** ile toplu çalıştır (onay gerekir)
3. Uzun süren görevleri iptal edebilirsin

### Aktivite günlüğü

Temizlik sonrası **View Log** ile hata kayıtlarını incele; hata filtresi ve panoya kopyalama ile destek/bug raporu oluşturabilirsin. Loglar 30 gün sonra otomatik silinir.

---

## 🛡️ Güvenlik modeli (kullanıcı özeti)

Mac Sai veri kaybını önlemek için tasarlanmıştır:

| Önlem | Açıklama |
| ----- | -------- |
| **Korumalı yollar** | `/System`, `/usr`, Apple sistem uygulamaları dokunulmaz |
| **Çöp Kutusu önceliği** | Silme varsayılan olarak geri alınabilir |
| **Dry-run** | Silmeden önce ne olacağını önizle |
| **SafetyGuard** | Her yol silinmeden önce doğrulanır; symlink saldırılarına karşı koruma |
| **Notarize + imza** | Apple her sürümü tarar; değiştirilmiş dosya açılmaz |
| **Ağ erişimi yok** | Telemetri, analitik veya "phone home" yok |
| **Açık kaynak** | Kaynak kodu GitHub'da denetlenebilir |

---

## ⚠️ Bilinen Sorunlar ve Çözümleri

| Sorun | Neden Olur | Çözüm |
| ----- | ---------- | ----- |
| Mail / Privacy / Malware modülleri boş | Tam Disk Erişimi yok | Sistem Ayarları → Tam Disk Erişimi → Mac Sai ekle; yeniden başlat |
| Homebrew'de `mac-sai` bulunamıyor | Tap eklenmemiş | `brew tap iliyami/macsai` çalıştır |
| Eski `mac-clean` kurulu | Yeniden adlandırma | Yukarıdaki geçiş komutlarını kullan |
| Maintenance sonrası yavaşlama | Spotlight yeniden indeksleme vb. | Normal; bir süre sonra düzelir |
| Updater bazı uygulamaları göstermiyor | Sparkle dışı güncelleme kanalları | [Latest](Latest.md) veya uygulamanın kendi güncellemesini kullan |
| Çok büyük temizlik seçimi | 50k+ öğe | Onay penceresi çıkar; iptal edilebilir parçalar halinde çalışır |

---

## 🔗 Faydalı Bağlantılar

- 💾 [GitHub Sayfası](https://github.com/iliyami/MacSai)
- 📦 [GitHub Releases](https://github.com/iliyami/MacSai/releases)
- 🍺 [Homebrew Tap (iliyami/macsai)](https://github.com/iliyami/homebrew-macsai)
- 📖 [Katkı rehberi](https://github.com/iliyami/MacSai/blob/main/CONTRIBUTING.md)
- 🔒 [Güvenlik politikası](https://github.com/iliyami/MacSai/blob/main/SECURITY.md)

---

## 📝 Notlar

> Mac Sai, CleanMyMac benzeri kapsamlı bir araç isteyip abonelik ödemek istemeyenler için güçlü bir seçenektir. [OnyX](https://www.titanium-software.fr/en/onyx.html) bakım scriptlerinde derin, [AppCleaner](AppCleaner.md) kaldırmada hafif kalır; Mac Sai ikisinin yanı sıra malware taraması, Space Lens ve menü çubuğu monitörünü tek pakette toplar. Agresif temizlik yapmadan önce Time Machine veya yedek al; özellikle Maintenance modülündeki yıkıcı görevleri okumadan **Run All** kullanma.

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
