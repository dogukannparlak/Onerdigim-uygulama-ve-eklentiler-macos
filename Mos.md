# 🛠️ Mos

> **Kısa Açıklama:** Harici fare tekerleği kaydırmayı macOS trackpad'ine yakın pürüzsüz harekete dönüştüren; uygulama bazlı profiller, eksen ayarları ve fare tuşu bağlama sunan ücretsiz, açık kaynaklı menü çubuğu aracı.

v4.2.1 · macOS 10.13+ (Apple Silicon / Intel) · CC BY-NC 4.0 / açık kaynak · Girdi / fare kaydırma

---

## 📌 Genel Bakış

macOS'ta fare tekerleği genelde sabit adımlarla sayfayı zıplatır; trackpad'deki akıcı atalet hissini vermez. Mos, tekerlek olaylarını yakalayıp adım, hız ve süre parametreleriyle yumuşatılmış kaydırmaya çevirir; fare hassasiyetini korur. Trackpad kullanmayıp harici fare veya trackball tercih edenler için en pratik ücretsiz çözümlerden biridir. Yalnızca kaydırma yönünü ters çevirmek isteyenler için [Scroll Reverser](https://pilotmoon.com/scrollreverser/) yeterli olabilir; imleç hızlandırma ve genel cihaz özelleştirmesi arayanlar [LinearMouse](https://linearmouse.app/) gibi daha geniş kapsamlı araçlara bakabilir. Mos ise odaklı bir tekerlek yumuşatma aracıdır - per-app profiller, eksen bazlı ayarlar ve Logitech HID++ tuş desteğiyle öne çıkar.

---

## ✨ Öne Çıkan Özellikler

- **Pürüzsüz kaydırma** - Step, gain ve duration ile eğri ayarı; trackpad simülasyon modu
- **Bağımsız eksenler** - Dikey ve yatay kaydırma için ayrı yumuşatma ve ters çevirme
- **Uygulama profilleri** - Her uygulama global ayarları miras alabilir veya kendi kaydırma/kısayol/tuş davranışını tanımlayabilir
- **Kaydırma kısayolları** - Hızlandırma, eksen dönüşümü ve geçici yumuşatma kapatma için özel tuşlar
- **Fare tuşu bağlama** - Fare, klavye veya özel olayları Mission Control, Spaces, ekran görüntüsü, uygulama, betik ve dosya açma gibi eylemlere bağla
- **Eylem kütüphanesi** - Finder, belge düzenleme, fare kaydırma ve sistem eylemleri için hazır aksiyonlar
- **Logitech HID++ desteği** - Bolt, Unifying ve Bluetooth üzerinden bağlı Logitech cihazlarında tuş olayları
- **Tamamen ücretsiz** - Açık kaynak ([CC BY-NC 4.0](https://github.com/Caldis/Mos/blob/master/LICENSE)); Mac App Store'a yüklenemez

---

## 📥 İndirme ve Kurulum

### Yöntem 1: Homebrew (Önerilen)

```bash
brew install --cask mos
```

Güncelleme:

```bash
brew update
brew upgrade --cask mos
```

> Homebrew yüklü değilse: [brew.sh](https://brew.sh) adresindeki komutu Terminal'de çalıştır.

### Yöntem 2: GitHub Releases

1. [GitHub Releases](https://github.com/Caldis/Mos/releases/latest) sayfasına git
2. En güncel sürümü indir ve arşivi aç
3. `Mos.app` dosyasını **Applications** klasörüne taşı
4. Gatekeeper uyarısı çıkarsa: Sistem Ayarları → Gizlilik ve Güvenlik → Yine de Aç

> v4.0.0-beta-20251105 ve sonrası imzalı ve notarize edilmiştir; eski sürümlerde ek Gatekeeper adımları gerekebilir.

---

## ⚙️ İlk Kurulum ve Önerilen Ayarlar

1. **Erişilebilirlik izni (zorunlu):** Mos tekerlek olaylarını okuyup yeniden yazmak için bu izne ihtiyaç duyar → Sistem Ayarları → Gizlilik ve Güvenlik → **Erişilebilirlik** → Mos'u etkinleştir
2. **Girişte başlat:** Mos ayarlarından veya Sistem Ayarları → Genel → Giriş Öğeleri ile oturum açılışında başlat
3. **Global kaydırma eğrisi:** Menü çubuğu simgesi → **Feel** - Step, Speed ve Duration ile trackpad'e yakın bir his ayarla; önizleme panelinden dene
4. **Trackpad'i hariç tut:** Dahili trackpad zaten akıcıysa Mos ayarlarında trackpad için yumuşatmayı devre dışı bırak; yalnızca harici fare etkilensin
5. **Uygulama profilleri:** Kod editörü, tarayıcı veya oyun gibi farklı kaydırma isteyen uygulamalar için **Profiles** bölümünden özel profil oluştur
6. **Logitech fare:** Logitech G HUB ile birlikte kullanıyorsan Mos'un HID++ desteğini dene; tuş bağlama için **Buttons** sekmesini kullan

> 💡 İlk kurulumda kaydırma değişmiyorsa izin listesinde Mos görünse bile TCC eşleşmesi bozulmuş olabilir - aşağıdaki "Bilinen Sorunlar" bölümündeki yeniden yetkilendirme adımlarını uygula.

---

## 🚀 Temel Kullanım

### Kaydırma hissini ayarlama

1. Menü çubuğundaki Mos simgesine tıkla → **Feel**
2. **Step** (adım), **Speed** (hız çarpanı) ve **Duration** (atalet süresi) kaydırıcılarını ayarla
3. Önizleme alanında ham ve yumuşatılmış kaydırmayı karşılaştır
4. Dikey ve yatay eksen için ayrı ayrı ters çevirme ve yumuşatma tanımlayabilirsin

### Uygulama bazlı profil

1. **Profiles** sekmesine git
2. Listeden uygulamayı seç veya **+** ile ekle
3. Global ayarları miras al veya yalnızca o uygulama için farklı step/speed/duration belirle
4. Örnek: Xcode'ta daha hassas, tarayıcıda daha akıcı kaydırma

### Fare tuşu bağlama

1. **Buttons** sekmesine git
2. Bağlamak istediğin fare tuşunu seç (Button 4, Button 5, tekerlek tıklaması vb.)
3. Eylem kütüphanesinden hazır aksiyon seç (Mission Control, Next Space, App Switcher…) veya kısayol/komut/betik ata
4. Logitech cihazlarda HID++ olayları doğrudan Mos üzerinden yakalanabilir

### Kaydırma kısayolları

Mos, geçici hızlandırma, eksen dönüşümü veya yumuşatmayı anlık kapatma için özel tuş atamayı destekler. Ayarlar → **Hotkeys** (veya ilgili profil sekmesi) altından tanımla.

> Aşağıdaki örnekler tipik kullanım senaryolarıdır; gerçek kısayollar Mos ayarlarından özelleştirilir.

| Senaryo | Davranış |
| ------- | -------- |
| **Genel web gezintisi** | Global Feel ayarıyla akıcı dikey kaydırma |
| **Yatay kaydırma** | Bağımsız X ekseni ayarı; timeline veya tablo uygulamalarında faydalı |
| **Oyun / CAD** | İlgili uygulama profilinde yumuşatmayı kapat veya step'i düşür |
| **Logitech yan tuşlar** | Button 4/5 → Mission Control, Space değiştirme vb. |

---

## ⚠️ Bilinen Sorunlar ve Çözümleri

| Sorun | Neden Olur | Çözüm |
| ----- | ---------- | ----- |
| Mos açılıyor ama kaydırma değişmiyor | Erişilebilirlik izni TCC eşleşmesi bozulmuş (güncelleme, taşıma, yeniden imzalama) | Mos'u kapat → Erişilebilirlik listesinden kaldır → `/Applications/Mos.app`'i yeniden ekle ve aç; gerekirse `tccutil reset Accessibility com.caldis.Mos` |
| Güncelleme sonrası izin etkisiz | macOS izin kaydı eski binary ile eşleşmiyor | Yukarıdaki yeniden yetkilendirme adımları; ardından Mos'u yeniden başlat |
| Gatekeeper uygulamayı engelliyor | İndirilen dosyada quarantine bayrağı veya imza sorunu | Sistem Ayarları → Yine de Aç; veya `xattr -dr com.apple.quarantine /Applications/Mos.app` |
| Belirli uygulamada garip kaydırma | Uygulama kendi kaydırma mantığını kullanıyor | **Profiles** ile o uygulama için ayrı profil; yumuşatmayı kapat veya step/speed ayarla |
| Logitech tuşu çalışmıyor | Cihaz Bolt/Unifying/Bluetooth üzerinden tanınmıyor veya G HUB çakışması | Bağlantı türünü kontrol et; Mos **Buttons** sekmesinde olayı görünüyor mu bak; G HUB'da çakışan atamayı kaldır |
| Trackpad de etkileniyor | Global ayar tüm cihazlara uygulanıyor | Mos ayarlarında trackpad için yumuşatmayı devre dışı bırak |
| LinearMouse / benzeri araçla çakışma | Birden fazla girdi aracı aynı olayları yakalıyor | Yalnızca birini aktif tut veya Mos'ta ilgili özelliği kapat |

---

## 🔗 Faydalı Bağlantılar

- 🌐 [Resmi Web Sitesi](https://mos.caldis.me/)
- 💾 [GitHub Sayfası](https://github.com/Caldis/Mos)
- 📦 [GitHub Releases](https://github.com/Caldis/Mos/releases/latest)
- 📖 [GitHub Wiki](https://github.com/Caldis/Mos/wiki)
- 📖 [İzin sorun giderme](https://github.com/Caldis/Mos/wiki/If-the-App-not-work-properly)
- 🗣️ [GitHub Discussions](https://github.com/Caldis/Mos/discussions)
- 📖 [Karşılaştırma rehberi](https://mos.caldis.me/compare/)
- 📦 [Homebrew Cask](https://formulae.brew.sh/cask/mos)

---

## 📝 Notlar

> Mos, harici fare kullanan Mac kullanıcıları için trackpad kalitesinde kaydırma deneyimi sunan olgun ve hafif bir araçtır. Yalnızca tekerlek yumuşatması değil; per-app profiller, tuş bağlama ve Logitech entegrasyonu da günlük iş akışını şekillendirmeye yarar. Lisans CC BY-NC 4.0 olduğu için ticari yeniden dağıtım kısıtlıdır; kişisel kullanım tamamen ücretsizdir. Mac App Store sürümü yoktur - resmi kaynak [mos.caldis.me](https://mos.caldis.me/) veya GitHub Releases'tır.

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
