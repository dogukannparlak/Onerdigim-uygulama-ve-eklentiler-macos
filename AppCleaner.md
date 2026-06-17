# 🛠️ AppCleaner

> **Kısa Açıklama:** macOS'ta uygulamaları yalnızca `.app` dosyası değil; tercih, önbellek ve destek dosyalarıyla birlikte tamamen kaldıran ücretsiz kaldırma aracı.

v3.6.8 · macOS 10.14+ (Apple Silicon / Intel) · Ücretsiz · Sistem / Bakım

---

## 📌 Genel Bakış

macOS'ta bir uygulamayı Çöp Kutusu'na sürüklemek çoğu zaman yalnızca ana `.app` dosyasını siler; `~/Library` altındaki tercih dosyaları, önbellekler ve destek klasörleri diskte kalır. AppCleaner, [FreeMacSoft](https://freemacsoft.net/) tarafından geliştirilen küçük ve güvenilir bir araçtır; kaldırmak istediğin uygulamayla ilişkili tüm dosyaları bulur, listeler ve onayınla birlikte siler. Sürükle-bırak arayüzü basittir; **SmartDelete** ile normal Çöp Kutusu alışkanlığını koruyarak arka planda temizlik yapabilirsin.

---

## ✨ Öne Çıkan Özellikler

- **Tam kaldırma** - Uygulama ile birlikte tercih, önbellek, çerez ve kütüphane dosyalarını da siler
- **Sürükle-bırak arayüzü** - Uygulamayı AppCleaner penceresine bırak; ilişkili dosyalar otomatik listelenir
- **Kurulu uygulama listesi** - Yüklü uygulamaları, eklentileri ve widget'ları listeden seçerek kaldır
- **SmartDelete** - Uygulamayı doğrudan Çöp Kutusu'na attığında ilişkili dosyaları silmek için sorar
- **Koruma ayarları** - Sistem uygulamalarını, çalışan uygulamaları veya seçtiğin uygulamaları yanlışlıkla silmeye karşı koru
- **Dosya arama (Lookup)** - Belirli bir dosya veya klasörün hangi uygulamaya ait olduğunu bul
- **Ücretsiz** - Reklamsız; her yeni macOS sürümü için güncellenir
- **Apple Silicon uyumlu** - Intel ve Apple Silicon Mac'lerde çalışır

---

## 📥 İndirme ve Kurulum

### Yöntem 1: Homebrew (Önerilen)

```bash
brew install --cask appcleaner
```

> Homebrew yüklü değilse: [brew.sh](https://brew.sh) adresindeki komutu Terminal'de çalıştır.

### Yöntem 2: Resmi İndirme

1. [freemacsoft.net/appcleaner](https://freemacsoft.net/appcleaner/) adresine git
2. macOS sürümüne uygun sürümü indir (**v3.6.8** - Mojave'den Tahoe'ya kadar)
3. `.dmg` dosyasını aç ve AppCleaner'ı **Applications** klasörüne sürükle
4. Gatekeeper uyarısı çıkarsa: Sistem Ayarları → Gizlilik ve Güvenlik → Yine de Aç

---

## ⚙️ İlk Kurulum ve Önerilen Ayarlar

1. **SmartDelete'i aç:** AppCleaner menü çubuğu → **AppCleaner → Preferences → SmartDelete → ON** - Çöp Kutusu'na attığın uygulamaların artık dosyalarını da temizler
2. **Sistem uygulamalarını koru:** **Preferences → General → Protect default OS X apps** - macOS'un yerleşik uygulamalarını yanlışlıkla silmeyi engeller
3. **Çalışan uygulamaları koru:** **Preferences → General → Protect running apps** - açık uygulamaların kaldırılmasını önler
4. **Kritik uygulamaları listeye ekle:** **Add additional apps to keep safe below** - AppCleaner, AltTab gibi sık kullandığın araçları koruma altına al
5. **Güncellemeleri kontrol et:** **Preferences → Updates → Check updates automatically**

> 💡 SmartDelete açıkken AppCleaner arka planda çalışabilir; menü çubuğunda simgesi görünür. Günlük kullanımda uygulamayı açmana gerek kalmadan temiz kaldırma yaparsın.

---

## 🚀 Temel Kullanım

### Sürükle-bırak ile kaldırma

1. AppCleaner'ı aç
2. Kaldırmak istediğin `.app` dosyasını (Applications veya başka bir konumdan) AppCleaner penceresine **sürükle-bırak**
3. Listelenen ilişkili dosyaları incele - istemediğin bir satırın işaretini kaldırabilirsin
4. **Remove** (Kaldır) butonuna tıkla
5. Yönetici parolasını gir

### Listeden kaldırma

1. AppCleaner penceresinde **Applications** sekmesine geç
2. Kaldırmak istediğin uygulamayı listeden seç
3. **Search** / arama ile uygulamayı bul, ardından kaldır

### SmartDelete ile kaldırma

1. SmartDelete açık olsun (yukarıdaki ayarlara bak)
2. Uygulamayı her zamanki gibi **Çöp Kutusu'na sürükle**
3. AppCleaner ilişkili dosyaları bulunca açılan pencerede **Remove**'a tıkla

### Klavye kısayolları

AppCleaner minimal bir aracıdır; temel işlemler fare ve sürükle-bırak ile yapılır. Menü kısayolları:

| Kısayol | İşlev |
| ------- | ----- |
| `Cmd + ,` | Tercihler (Preferences) |
| `Cmd + Q` | AppCleaner'dan çık |

---

## ⚠️ Bilinen Sorunlar ve Çözümleri

| Sorun | Neden Olur | Çözüm |
| ----- | ---------- | ----- |
| Uygulama kaldırılamıyor, "protected" uyarısı | Koruma ayarları aktif | Preferences → General → ilgili koruma seçeneğini kapat veya uygulamayı koruma listesinden çıkar |
| Çalışan uygulama silinmiyor | **Protect running apps** açık | Uygulamayı önce kapat, sonra tekrar dene |
| SmartDelete tetiklenmiyor | Özellik kapalı veya AppCleaner çalışmıyor | Preferences → SmartDelete → ON; AppCleaner'ı bir kez açıp kapat |
| Bazı dosyalar listede görünmüyor | Uygulama dosyaları standart konum dışında | **Lookup** ile dosyayı manuel ara veya uygulamanın kendi kaldırma aracını kullan |
| Yanlışlıkla dosya silindi | Onay ekranı atlandı | Çöp Kutusu boşaltılmadıysa dosyaları geri yükle; `.app`'i Applications'a geri taşı |

---

## 🔗 Faydalı Bağlantılar

- 🌐 [Resmi Web Sitesi](https://freemacsoft.net/appcleaner/)
- 🏠 [FreeMacSoft Ana Sayfa](https://freemacsoft.net/)
- 📦 [Homebrew Cask](https://formulae.brew.sh/cask/appcleaner)

---

## 📝 Notlar

> AppCleaner kapalı kaynaklı, ücretsiz bir macOS aracıdır; resmi kaynak [FreeMacSoft](https://freemacsoft.net/appcleaner/) sitesidir. Arayüz yalnızca İngilizcedir ancak kullanımı son derece basittir. Toplu kaldırma desteklemez - uygulamaları tek tek silmen gerekir. PearCleaner gibi alternatifler yetim dosya taraması sunar; AppCleaner'ın güçlü yanı **SmartDelete** ve yıllardır güncel kalmasıdır. Kaldırmadan önce listedeki dosyaları gözden geçirmeni öneririm; nadiren de olsa başka bir uygulamanın paylaştığı dosya görünebilir.

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
