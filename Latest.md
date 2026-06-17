# 🛠️ Latest

> **Kısa Açıklama:** Mac'teki uygulamaların güncel olup olmadığını tek yerden kontrol eden, sürüm notlarını gösteren ve birçok uygulamayı uygulama içinden güncelleyebilen ücretsiz, açık kaynaklı bir güncelleme aracı.

v0.11 · macOS 10.13+ (Apple Silicon / Intel) · GPL-3.0 / açık kaynak · Sistem / Bakım

---

## 📌 Genel Bakış

Mac'te onlarca uygulama kuruluysa hangisinin güncel, hangisinin eski kaldığını takip etmek zordur. Mac App Store uygulamaları App Store'dan, Sparkle kullanan uygulamalar kendi güncelleme penceresinden, Homebrew ile kurulanlar Terminal'den güncellenir — hepsini ayrı ayrı kontrol etmek zaman alır.

**Latest**, yüklü uygulamaları tarar; güncelleme var mı gösterir, ne değiştiğini sürüm notlarıyla özetler ve desteklenen uygulamaları doğrudan Latest içinden güncellemen sağlar. Mac App Store, Sparkle (çoğu üçüncü taraf uygulama) ve **Homebrew Cask** kaynaklarını destekler. Tamamen ücretsiz ve açık kaynaklıdır; geliştirici boş zamanında sürdürür.

---

## ✨ Öne Çıkan Özellikler

- **Çoklu kaynak desteği** — Mac App Store, Sparkle tabanlı uygulamalar ve Homebrew Cask
- **Tek ekranda genel bakış** — Hangi uygulamaların güncellenebileceğini listeler; kaynak simgesi (App Store / Web) gösterir
- **Sürüm notları** — Güncelleme veya kurulu sürüm için değişiklikleri tek, düzenli arayüzde oku
- **Uygulama içinden güncelleme** — Desteklenen uygulamaları Latest'ten güncelle; **Update All** ile toplu güncelleme
- **Kurulu güncellemeler geçmişi** — Dün kurduğun güncellemede ne değiştiğini geriye dönük gör
- **Uygulama yok sayma** — Belirli uygulamaları güncelleme listesinden hariç tut
- **Arama** — Uygulama adına göre hızlı filtrele
- **Sıralama** — Varsayılan: son güncellenenler; menüden ada göre sıralama
- **Desteklenmeyen uygulamalar** — Listede soluk gösterilir; isteğe bağlı gizlenebilir
- **Touch Bar desteği** — Uyumlu MacBook'larda listede gezin, sürüm notlarını oku, toplu güncelle
- **Türkçe dahil çoklu dil** — Weblate üzerinden topluluk çevirileri

---

## 📥 İndirme ve Kurulum

### Yöntem 1: Homebrew (Önerilen)

```bash
brew install --cask latest
```

> Homebrew yüklü değilse: [brew.sh](https://brew.sh) adresindeki komutu Terminal'de çalıştır.

### Yöntem 2: Resmi İndirme

1. [max.codes/latest](https://max.codes/latest/) adresine git veya [GitHub Releases](https://github.com/mangerlahn/Latest/releases) sayfasından güncel sürümü indir
2. `.zip` arşivini aç (çift tıkla)
3. `Latest.app` dosyasını **Applications** klasörüne taşı
4. Gatekeeper uyarısı çıkarsa: Sistem Ayarları → Gizlilik ve Güvenlik → Yine de Aç

---

## ⚙️ İlk Kurulum ve Önerilen Ayarlar

1. **İlk tarama:** Latest'i aç — yüklü uygulamalar otomatik taranır; güncelleme varsa listede görünür
2. **Güncellemeleri periyodik kontrol:** Menü → **Latest → Check for Updates** veya uygulamayı ara sıra aç
3. **Yok sayılacak uygulamalar:** Güncellemek istemediğin uygulamaya sağ tık → **Ignore** — beta sürüm kullanan veya manuel güncellediğin uygulamalar için faydalı
4. **Desteklenmeyen uygulamalar:** Ayarlardan desteklenmeyen uygulamaları listede göster/gizle seçeneğini ihtiyacına göre ayarla
5. **Dil:** Sistem dilin Türkçe ise arayüz Türkçe görünür (0.10.1+)

> 💡 Latest, [Applite](Applite.md) ile birlikte iyi çalışır: Applite ile Homebrew uygulamalarını kurarsın, Latest ile Mac App Store ve Sparkle uygulamalarının yanı sıra Cask güncellemelerini de takip edersin. Setapp klasöründeki uygulamalar varsayılan olarak yok sayılır.

---

## 🚀 Temel Kullanım

### Güncelleme kontrolü

1. Latest'i aç
2. Liste otomatik dolar — güncelleme olan uygulamalar üstte veya vurgulu görünür
3. Bir uygulamaya tıkla → sağ tarafta sürüm notlarını oku
4. **Update** ile tek uygulamayı güncelle veya araç çubuğundan **Update All** ile desteklenen tümünü güncelle

### Kurulu güncellemeleri inceleme

Güncel uygulamalar için de sürüm notlarına bakabilirsin — "dün kurduğum güncellemede ne vardı?" sorusuna yanıt verir. Listeden güncel bir uygulama seç; değişiklik özeti uniform tasarımla gösterilir.

### Uygulama yok sayma

1. Listede uygulamaya **sağ tık**
2. **Ignore** seç
3. Yok sayılan uygulamaları ayrı görmek için menüden ilgili görünüm seçeneğini kullan

### Arama ve sıralama

- Üstteki arama kutusuna uygulama adını yaz — listeyi filtrele
- **View → Sort By → Name** ile ada göre sırala (varsayılan: son güncellenenler)

### Kaynak türleri

| Simge / kaynak | Anlam |
| -------------- | ----- |
| Mac App Store | App Store'dan indirilen uygulama |
| Web (Sparkle) | Kendi güncelleme mekanizması olan uygulama |
| Homebrew Cask | `brew install --cask` ile kurulan uygulama |

Desteklenmeyen uygulamalar listede soluk görünür; Latest bunları güncelleyemez.

---

## ⚠️ Bilinen Sorunlar ve Çözümleri

| Sorun | Neden Olur | Çözüm |
| ----- | ---------- | ----- |
| Uygulama listesi boş | Spotlight devre dışı veya indeks gecikmesi | Spotlight'ı aç; Latest'i yeniden başlat. Sorun sürerse GitHub Issues'a bak |
| Güncelleme var sanıyor ama güncel | Yanlış sürüm eşlemesi (özellikle Cask) | Latest'i güncelle; 0.10+ sürümlerde Homebrew kontrolü iyileştirildi |
| Bazı uygulamalar listede yok | Sparkle/DevMate dışı özel güncelleme | Bilinen sınırlama; manuel güncelle |
| Mac App Store uygulaması Latest'ten güncellenmiyor | Uygulama veya macOS kısıtı | App Store'dan manuel güncelle |
| Setapp uygulamaları görünmüyor | Setapp klasörü bilinçli yok sayılır | Setapp kendi güncelleme kanalını kullanır |

---

## 🔗 Faydalı Bağlantılar

- 🌐 [Resmi Web Sitesi](https://max.codes/latest/)
- 💾 [GitHub Sayfası](https://github.com/mangerlahn/Latest)
- 📦 [GitHub Releases](https://github.com/mangerlahn/Latest/releases)
- 🌍 [Çeviri katkısı (Weblate)](https://hosted.weblate.org/engage/latest/)
- 📦 [Homebrew Cask](https://formulae.brew.sh/cask/latest)
- 💝 [Geliştirmeyi destekle](https://max.codes/latest/donate)

---

## 📝 Notlar

> Latest, Mac'te dağınık güncelleme kanallarını tek pencerede toplamak için en pratik ücretsiz araçlardan biridir. App Store ve Sparkle dışındaki uygulamalar (Adobe, Microsoft 365 abonelik uygulamaları vb.) genelde desteklenmez. Homebrew kullanıyorsan `brew upgrade --cask` de güncelleme yapar; Latest bunu görsel arayüzle birleştirir. Tam kaldırma için [AppCleaner](AppCleaner.md), Cask kurulumu için [Applite](Applite.md) ile birlikte düşünülebilir.

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
