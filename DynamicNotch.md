# 🛠️ DynamicNotch

> **Kısa Açıklama:** Notch'lu MacBook'larda çentiği canlı bir sistem yüzeyine dönüştüren; medya, indirme, AirDrop, zamanlayıcı, ekran kaydı, bağlantı olayları ve yerel HUD'lar sunan ücretsiz, açık kaynaklı bir macOS aracı.

v1.5.1 · macOS 14.6+ (Apple Silicon / Intel) · GPL-3.0 / açık kaynak · Notch / sistem arayüzü

---

## 📌 Genel Bakış

MacBook'un üstündeki notch çoğu zaman boş veya menü çubuğuyla birleşik bir alan olarak kalır; sistem olayları ise ayrı bildirimler ve macOS HUD'larıyla dağılır. **DynamicNotch**, iPhone'daki Dynamic Island mantığını Mac'e taşır: çentik normalde donanım şeklinde durur, bir olay olduğunda genişleyip kuyruk tabanlı animasyonlarla içerik gösterir.

SwiftUI ve AppKit ile yazıldığı için web tarzı bir overlay yerine yerel macOS hissi verir. Notch'u olmayan Mac'lerde (iMac, Mac mini, harici monitör) otomatik olarak yüzen Dynamic Island kapsülüne geçer. [NotchNook](https://formulae.brew.sh/cask/notchnook) veya [Boring Notch](https://github.com/TheBoredTeam/boring.notch) gibi alternatiflere kıyasla kendi motoru üzerine kurulu; animasyon ve etkileşimleri iPhone Dynamic Island davranışına yakın tutmayı hedefler.

> ⚠️ Uygulama henüz **kod imzalı değil**; ilk açılışta Gatekeeper uyarısı çıkabilir. Aşağıdaki kurulum adımlarını izle.

---

## ✨ Öne Çıkan Özellikler

- **Live Activities** — Now Playing (medya kontrolü, albüm kapağı, ses görselleştirici), indirme ilerlemesi, AirDrop, zamanlayıcı, ekran kaydı göstergesi, takvim etkinlikleri, Odak modu, Kişisel Erişim Noktası ve kilit ekranı widget'ları
- **Dynamic Island modu** — Fiziksel notch olmayan ekranlarda yüzen kapsül şekline geçiş; harici monitörlere de Dynamic Island eklenebilir
- **Geçici uyarılar** — Pil düşük/tak/çıkar/tam şarj, Wi-Fi kopma/bağlanma, Bluetooth, VPN, Odak modu değişimi
- **Yerel HUD yerine geçme** — Ses, ekran parlaklığı ve klavye arka ışığı göstergeleri menü çubuğu yerine çentik içinde görünür
- **Sürükle-bırak** — Dosya veya klasörü çentiğe bırak: AirDrop, Tray (bekletme) veya Convert (sıkıştırma)
- **Çentikten zamanlayıcı** — Homepage'de Timer'ı öne alarak doğrudan çentikten sayaç başlat
- **Kamera önizlemesi** — Çentik içinde kamera canlı önizlemesi (izin gerekir)
- **Aktivite önceliği** — Aynı anda birden fazla olay varken hangisinin çentikte görüneceğini puanla belirle
- **Şarkı sözleri** — LRCLIB (senkron karaoke) + Lyrics.ovh yedek sağlayıcı ile çift API motoru
- **Jestler** — Tıkla-bas, hover ile açma, trackpad kaydırma, dikey kaydırarak kapat/geri getir
- **Derin özelleştirme** — Notch genişlik/yükseklik, çerçeve, arka plan, animasyon preset'leri, ekran seçimi, menü çubuğu/Dock simge görünürlüğü
- **Çoklu dil** — İngilizce, Rusça, İspanyolca, Basitleştirilmiş Çince (+ sistem dili)

---

## 📥 İndirme ve Kurulum

### Yöntem 1: GitHub Releases (Önerilen)

Homebrew Cask'te henüz resmi bir `dynamicnotch` formülü yok; en güncel sürüm GitHub Releases üzerinden dağıtılıyor.

1. [GitHub Releases](https://github.com/jackson-storm/DynamicNotch/releases/latest) sayfasına git
2. `DynamicNotch_v1.5.1.dmg` (veya en güncel `.dmg`) dosyasını indir
3. `DynamicNotch.app` dosyasını **Applications** klasörüne sürükle
4. İlk açılış için aşağıdaki Gatekeeper adımlarını uygula

**İlk açılış (imzasız uygulama):**

1. **Applications** içinde DynamicNotch'a **sağ tık** → **Open** (Aç)
2. Uyarı çıkınca **Cancel** (İptal) de
3. **Sistem Ayarları → Gizlilik ve Güvenlik** → **Security** bölümünde **Open Anyway** (Yine de Aç)
4. Mac parolanı gir → **Open** (Aç)

> ⚠️ Yalnızca [github.com/jackson-storm/DynamicNotch](https://github.com/jackson-storm/DynamicNotch) veya [resmi web sitesi](https://dynamicnotch.evgeniy-petrukovich.workers.dev) üzerinden indir.

### Yöntem 2: Kaynaktan derleme

```bash
git clone https://github.com/jackson-storm/DynamicNotch.git
cd DynamicNotch
open DynamicNotch.xcodeproj
```

Xcode'da `DynamicNotch` şemasını çalıştır. Swift Package Manager bağımlılıkları proje tarafından çözülür.

---

## ⚙️ İlk Kurulum ve Önerilen Ayarlar

1. **Onboarding sihirbazı:** İlk açılışta özellik tanıtımı ve izin adımlarını tamamla
2. **Ekran seçimi:** Menü çubuğundan ayarları aç → **General** → **Location** — DynamicNotch'un hangi ekranda görüneceğini seç (harici monitör dahil)
3. **Simge görünürlüğü:** Aynı **General** sekmesinde menü çubuğu ve Dock simgesinin görünürlüğünü ayarla
4. **Erişilebilirlik (HUD ve sistem etkileşimi için):** Sistem Ayarları → Gizlilik ve Güvenlik → **Erişilebilirlik** → DynamicNotch'u etkinleştir
5. **Ekran kaydı (ses görselleştirici için):** Now Playing görselleştiricisi istiyorsan → **Ekran ve Sistem Ses Kaydı** → DynamicNotch ekle
6. **Bluetooth (aksesuar durumu için):** Bluetooth erişim isteğini onayla
7. **Medya / Now Playing:** macOS'un istediği medya erişim izinlerini ver
8. **Girişte başlat:** Ayarlardan oturum açılışında başlatmayı etkinleştir
9. **Açılış davranışı:** **Notch** sekmesinin altında çentiğin **tıkla-bas** mı yoksa **üzerine gelince** mi açılacağını seç — hover modu medya kontrolleri için pratiktir
10. **Aktivite önceliği:** **Notch** sekmesinde her aktiviteye öncelik puanı ver — aynı anda ekran kaydı ve müzik çalıyorsa yüksek puanlı olan çentikte görünür
11. **Çentikten zamanlayıcı:** **Homepage** sekmesinde **Timer** özelliğine çift tıkla ve ilk sıraya taşı — böylece çentiğe tıklayınca doğrudan sayaç başlatabilirsin
12. **Notch görünümü:** Çerçeveyi kapat, genişlik/yükseklik ve animasyon preset'ini tercihine göre ayarla
13. **Tam ekran davranışı:** Tam ekran uygulamalarda notch'u gizleme/geri yükleme seçeneğini kontrol et — varsayılan olarak tam ekranda gizlenir, çıkınca etkinlikler geri gelir

> 💡 Tüm izinleri vermek zorunda değilsin; yalnızca kullanacağın özellikler için gerekli olanları aç. Kamera önizlemesini denemek istiyorsan ekran kaydı aktivitesinin çentiği kaplamadığından emin ol — gerekirse **Notch** sekmesinden ekran kaydı önceliğini geçici olarak düşür veya aktiviteyi kaydırarak kapat.

---

## 🚀 Temel Kullanım

### Ekran ve simge ayarları

1. Menü çubuğundaki DynamicNotch simgesine tıkla → **Settings** (Ayarlar)
2. **General → Location** — çentiğin görüneceği ekranı seç (dahili MacBook ekranı veya harici monitör)
3. Üst kısımdan menü çubuğu ve Dock simgesinin görünürlüğünü kapat/aç

### Yerleşik HUD'lar (ses, parlaklık, klavye arka ışığı)

macOS'ta ses, parlaklık veya klavye arka ışığını değiştirdiğinde gösterge artık menü çubuğunda değil **çentik içinde** belirir. Bunun için **Erişilebilirlik** izni gerekir.

### Now Playing ve medya kontrolü

1. Spotify, Apple Music veya desteklenen bir uygulamada müzik/video çal
2. Notch kompakt modda oynatılan içeriği gösterir
3. Varsayılan: çentiğe **tıkla ve basılı tut** — genişleyerek medya kontrolleri açılır
4. **Notch** ayarlarından **hover ile aç** moduna geçersen üzerine gelince kontroller açılır
5. Dikey kaydırma veya yatay scroll ile canlı aktiviteyi kapatabilirsin

### Aktivite önceliği (çakışan olaylar)

Aynı anda birden fazla olay olabilir (ör. ekran kaydı + müzik). Hangisinin çentikte görüneceği **Notch** sekmesindeki öncelik puanına bağlıdır:

1. **Settings → Notch** sekmesine git
2. Her aktiviteye öncelik puanı ver (Now Playing, Screen Recording, Timer vb.)
3. Yüksek puanlı aktivite çentikte öne çıkar — örneğin ekran kaydı alırken müzik çalıyorsan kayıt göstergesini görmek için ekran kaydının önceliğini artır

### Zamanlayıcı ve takvim

- **Zamanlayıcı:** Sistem zamanlayıcısı veya çentikten başlattığın sayaç kompakt geri sayım olarak görünür
- **Çentikten başlatma:** **Homepage** sekmesinde **Timer**'ı çift tıkla → ilk sıraya sürükle → çentiğe tıklayınca sayaç başlat
- **Takvim:** Yaklaşan etkinlikler çentikte hatırlatma olarak belirir

### Ekran kaydı göstergesi

Ekran kaydı alırken çentikte kayıt göstergesi görünür. Öncelik düşükse Now Playing gibi başka bir aktivite onun yerine geçebilir — **Notch** sekmesinden önceliği ayarla veya kayıt bitene kadar diğer aktiviteyi kaydırarak kapat.

### Sürükle-bırak

1. Bir veya birden fazla dosya/klasörü tut
2. Çentiğe sürükle ve bırak
3. Üç seçenek çıkar:

| Seçenek | Ne yapar |
| ------- | -------- |
| **AirDrop** | Dosyayı AirDrop ile gönder |
| **Tray** | Dosyayı bekletme alanına koy; daha sonra tekrar kullan |
| **Convert** | Dosyayı sıkıştır / dönüştür |

### İndirme, AirDrop ve bağlantı olayları

- **İndirme:** Safari veya Finder indirmeleri çentikte ilerleme çubuğu olarak görünür
- **AirDrop:** Dosya alımı sırasında çentik genişler
- **Wi-Fi:** Bağlantı koptuğunda veya yeniden bağlandığında çentikte bildirim
- **Odak modu:** Odak modu değiştiğinde çentikte gösterilir

### Pil uyarıları

Pil yüzdesi düştüğünde, şarja takıldığında ve tam şarj olduğunda çentikte kısa süreli uyarılar belirir.

### Kamera önizlemesi

Kamera özelliğini etkinleştirerek çentik içinde canlı kamera önizlemesi gösterebilirsin. Ekran kaydı aktivitesi aktifken önizleme görünmeyebilir — önceliği düşür veya kayıt aktivitesini kapat.

### Kilit ekranı widget'ları

DynamicNotch kilit ekranına da widget'lar ekler (medya, pil vb.). Kilit ekranı davranışı macOS sürümüne göre farklılık gösterebilir.

### Notch'u olmayan ekranlarda

Harici monitör veya notch'suz Mac kullanıyorsan uygulama otomatik olarak ekranın üst ortasında yüzen Dynamic Island kapsülüne geçer. **General → Location** ile hangi ekranda görüneceğini seçebilirsin.

### Jestler ve etkileşim

| Hareket | İşlev |
| ------- | ----- |
| Tıkla ve basılı tut | Çentiği genişlet (varsayılan) |
| Üzerine gel (hover modu) | Medya kontrollerini aç |
| Dikey kaydır (trackpad) | Canlı aktiviteyi kapat / geri getir |
| Yatay scroll / kaydır | Aktiviteyi kapat |

---

## ⚠️ Bilinen Sorunlar ve Çözümleri

| Sorun | Neden Olur | Çözüm |
| ----- | ---------- | ----- |
| macOS uygulamayı engelliyor | Henüz kod imzalı değil | Sağ tık → Open veya Gizlilik ve Güvenlik → Open Anyway |
| Medya / görselleştirici çalışmıyor | Ekran kaydı veya medya izni yok | İlgili izinleri ver; uygulamayı yeniden başlat |
| HUD'lar değişmiyor | Erişilebilirlik izni yok | Sistem Ayarları → Erişilebilirlik → DynamicNotch açık olsun |
| Kilit ekranı davranışı tutarsız | Özel macOS API'lerine dayanıyor | macOS sürümüne göre farklılık gösterebilir; güncel sürümü kullan |
| Tam ekranda notch kayboldu | Bilinçli tasarım | Tam ekrandan çıkınca aktiviteler geri yüklenir |
| Ekran kaydı çentikte görünmüyor | Now Playing önceliği daha yüksek | **Notch** sekmesinde Screen Recording önceliğini artır |
| Kamera önizlemesi görünmüyor | Ekran kaydı aktivitesi önde | Kayıt aktivitesini kapat veya önceliğini düşür |
| Homebrew ile kurulamıyor | Resmi Cask henüz yok | GitHub Releases'ten indir |

---

## 🔗 Faydalı Bağlantılar

- 🌐 [Resmi Web Sitesi](https://dynamicnotch.evgeniy-petrukovich.workers.dev)
- 💾 [GitHub Sayfası](https://github.com/jackson-storm/DynamicNotch)
- 📦 [GitHub Releases](https://github.com/jackson-storm/DynamicNotch/releases/latest)
- 🐛 [GitHub Issues](https://github.com/jackson-storm/DynamicNotch/issues)
- 🎬 [YouTube inceleme / tanıtım](https://www.youtube.com/watch?v=Wdl3UmSWZWs)
- 📢 [Telegram kanalı (güncellemeler)](https://t.me/Dynamic_Notch)
- 💬 [Telegram (geliştirici)](https://t.me/id10101101)

---

## 📝 Notlar

> DynamicNotch, notch'lu MacBook sahipleri için menü çubuğunu daha işlevsel kullanmak isteyenlere güçlü bir seçenek. Medya, indirme ve sistem olaylarını tek bir yerde toplar; jestler ve animasyonlar iPhone Dynamic Island'a yakın bir deneyim sunar. Notch'u olmayan makinelerde de v1.5.1 ile yüzen kapsül modu desteklenir. Daha hafif veya farklı bir yaklaşım arıyorsan Homebrew'deki [notchnook](https://formulae.brew.sh/cask/notchnook) veya [topnotch](https://formulae.brew.sh/cask/topnotch) gibi alternatiflere bakabilirsin; DynamicNotch daha geniş özellik seti ve kendi animasyon motoruyla öne çıkar. Uygulama GPL-3.0 lisanslıdır ve henüz notarize edilmemiştir — kurulumda Gatekeeper adımlarını atlamamaya dikkat et.

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
