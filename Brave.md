# 🛠️ Brave Browser

> **Kısa Açıklama:** Gizlilik odaklı Chromium tabanlı tarayıcı; yerleşik reklam/izleyici engelleme, parmak izi koruması ve cihazlar arası şifreli senkronizasyon.

Güncel · macOS (Apple Silicon / Intel) · Ücretsiz (Premium: VPN, Talk) · Tarayıcı

---

## 📌 Genel Bakış

Brave, Chromium altyapısı üzerine kurulu bağımsız bir tarayıcıdır. Chrome eklentileriyle uyumludur; asıl farkı varsayılan olarak açık gelen **Shields** katmanıdır: üçüncü taraf reklamlar, izleyiciler, parmak izi girişimleri ve birçok çerez pop-up'ı engellenir. Chrome veya Edge'e kıyasla daha az veri tüketir, sayfalar genelde daha hızlı açılır ve siteler arası izleme varsayılan olarak kısıtlanır.

Tarayıcı gizliliğini karşılaştırmak için [PrivacyTests.org](https://privacytests.org/) yararlı bir referanstır. Açık kaynak testlerle tarayıcıların izleme, çerez bölümleme (state partitioning) ve parmak izi korumasını yan yana gösterir; Brave varsayılan ayarlarla çoğu masaüstü tarayıcıya kıyasla güçlü sonuçlar verir.

---

## ✨ Öne Çıkan Özellikler

- **Shields** - Site bazlı reklam, izleyici ve parmak izi koruması
- **Üçüncü taraf çerez engelleme** - Siteler arası izleme için kullanılan çerezler kısıtlanır
- **HTTPS by Default (Bağlantıları HTTPS'e yükselt)** - Mümkün olduğunda HTTP bağlantıları HTTPS'e yükseltilir; Strict mod ile ek koruma
- **Çerez pop-up engelleme** - "Çerezleri kabul et" pencerelerini azaltır
- **Global Privacy Control (GPC)** - Veri satışını reddetme sinyali (varsayılan açık)
- **Brave Sync** - Uçtan uca şifreli cihazlar arası senkronizasyon; hesap gerekmez
- **Chrome eklenti uyumluluğu** - Chrome Web Store eklentileri çalışır
- **Gizli / Tor penceresi** - Yerel oturum izolasyonu; isteğe bağlı Tor üzerinden gezinme

---

## 📥 İndirme ve Kurulum

### Yöntem 1: Homebrew (Önerilen)

```bash
brew install --cask brave-browser
```

> Homebrew yüklü değilse: [brew.sh](https://brew.sh) adresindeki komutu Terminal'de çalıştır.

### Yöntem 2: Resmi İndirme

1. [brave.com/download](https://brave.com/download/) adresine git
2. **Get Brave** / indir butonuna tıkla
3. `.dmg` dosyasını aç ve Brave'i **Applications** klasörüne sürükle
4. İlk açılışta eski tarayıcıdan yer imleri, geçmiş ve ayarları içe aktarmayı seç (Chrome, Edge, Firefox, Safari desteklenir)
5. Gatekeeper uyarısı çıkarsa: Sistem Ayarları → Gizlilik ve Güvenlik → Yine de Aç

---

## ⚙️ İlk Kurulum ve Önerilen Ayarlar

Ayarlar sayfasına gitmek için adres çubuğuna `brave://settings/` yaz veya menüden **Ayarlar**'ı aç.

Bu rehberde her ayar kategorisi ayrı bölümde anlatılır. Aşağıdaki **Brave Ayarları** bölümüne bak:

1. **İçe aktarma:** İlk açılış ekranından yer imleri, şifreler ve geçmişi aktar
2. **Başlangıç davranışı:** `brave://settings/getStarted` → Başlangıçta ve Yeni Sekme Sayfası ayarları
3. **Shields:** Çoğu site için varsayılan ayar yeterli; site bozulursa adres çubuğundaki aslan simgesinden gevşet
4. **Arama motoru:** Tercih ettiğin motoru `brave://settings/search` üzerinden seç (aşağıdaki Arama motoru bölümüne bak)
5. **Brave Sync:** Birden fazla cihaz kullanıyorsan `brave://settings/braveSync` ile senkronizasyonu kur

> 💡 **İpucu:** Ayarları hızlıca açmak için `brave://settings/` yaz. Belirli bir bölüm için örneğin `brave://settings/shields` kullan.

---

## 🚀 Temel Kullanım

### Shields (Kalkanlar) ve reklam engelleme

1. Adres çubuğunun sağındaki **aslan simgesine** tıkla
2. Geçici olarak Shields'ı kapat veya izleyici/reklam engellemeyi ayarla
3. Kalıcı site ayarı için **Site ayarlarını yönet**'e git
4. Genel varsayılanlar için `brave://settings/shields` kullan

Shields şunları hedefler: üçüncü taraf reklamlar, cross-site izleyiciler, parmak izi girişimleri, bazı first-party reklamlar. Site düzgün çalışmıyorsa Shields'ı tamamen kapatmak yerine yalnızca ilgili özelliği (ör. izleyici engelleme) gevşetmek genelde yeterlidir.

### Gizlilik ve mahremiyet

- **Gizli pencere** (`Cmd + Shift + N`): Yerel geçmiş/çerez oturumu kapatılınca silinir; ISS veya site hâlâ trafiği görebilir
- **Tor penceresi** (etkinse): Menü → **Yeni gizli pencere (Tor)** - trafik Tor ağı üzerinden gider
- **GPC, HTTPS, çerez temizleme:** `brave://settings/privacy`
- **Karşılaştırma:** [PrivacyTests.org](https://privacytests.org/) ile Brave ve diğer tarayıcıların izleme test sonuçlarını incele

### Arama motoru değiştirme

1. `brave://settings/search` adresine git
2. **Normal pencere** veya **Özel pencere** satırında **Değiştir**'e tıkla
3. Özel motor eklemek için **Arama motorlarını ve site aramalarını yönetin** → **Ekle** (URL'de `%s` kullan)

Ayrıntılar: aşağıdaki **Arama motoru** ayar bölümü.

### Eklenti yükleme

1. `brave://extensions` adresine git
2. Chrome Web Store'dan eklenti yükle (Brave uyumludur)
3. Önerilen eklentiler için: [chrome-extensions/README.md](chrome-extensions/README.md)

---

## ⚙️ Brave Ayarları

`brave://settings/` menüsündeki her ayar kategorisi ayrı bölümde anlatılır.

---

### Başlayın

**Ayarlar yolu:** `brave://settings/getStarted`

Tarayıcıyı her açtığında ne olacağını ve yeni sekmelerin nasıl görüneceğini buradan ayarlarsın.

#### Başlangıçta

Brave açıldığında hangi sayfaların yükleneceğini seç:


| Seçenek                                       | Ne yapar                             | Ne zaman tercih edilir                                               |
| --------------------------------------------- | ------------------------------------ | -------------------------------------------------------------------- |
| **Yeni Sekme sayfasını aç**                   | Tek boş yeni sekme açılır            | Hızlı, sade başlangıç; her seferinde sıfırdan başlamak isteyenler    |
| **Kaldığım yerden devam et**                  | Son kapatılan sekmeler geri gelir    | Günlük kullanımda en pratik seçenek; açık kalan işleri kaybetmezsin  |
| **Belirli bir sayfayı veya sayfa grubunu aç** | Tanımladığın sabit sayfa(lar) açılır | Her açılışta aynı site (e-posta, panel, haber vb.) gelsin isteyenler |


Belirli sayfa grubu seçersen **Sayfa ekle** ile URL gir; birden fazla sayfa tanımlayabilirsin.

#### Yeni Sekme Sayfası

- **Yeni sekme sayfası gösteriyor:** Açılır listeden yeni sekmede ne görüneceğini seç (ör. **Anasayfa**)
- **Yeni sekme sayfasını özelleştir:** Kenar çubuğu, arka plan, widget'lar ve kısayollar için ayrı özelleştirme ekranını açar

**Anasayfa** seçeneği Brave'in kontrol panelini gösterir; engellenen reklam/izleyici özeti gibi bilgiler burada yer alabilir. Daha sade bir yeni sekme istiyorsan özelleştirme ekranından gereksiz widget'ları kapatabilirsin.

> 💡 **İpucu:** İlk kurulumda eski tarayıcıdan veri aktarımı ilk açılış ekranında sunulur. Yer imleri, şifreler ve geçmişi oradan içe aktarabilirsin; varsayılan tarayıcı yapma teklifi de genelde ilk açılışta gelir.

---

### Görünüm

**Ayarlar yolu:** `brave://settings/appearance`

Tarayıcının tema, adres çubuğu, sekmeler ve kenar çubuğu davranışını buradan ayarlarsın.

#### Tema ve araç çubuğu

- **Tema:** Açık / koyu tema ve renk şeması (harici tema sayfasına gider)
- **Araç çubuğunuzu özelleştirin:** Sağ panelden düğmeleri aç/kapat; araç çubuğundaki düğmeleri sürükleyerek yeniden sırala; **Varsayılana sıfırla** ile geri al
- **Ana Sayfa düğmesini göster:** Kapalı; adres çubuğunda yer kaplamaz

**Araç çubuğu düğmeleri** (`Araç çubuğunuzu özelleştirin` paneli):


| Bölüm                    | Düğme / seçenek              | Önerilen | Açıklama                                              |
| ------------------------ | ---------------------------- | -------- | ----------------------------------------------------- |
| **Gezinme**              | Ana Sayfa                    | Kapalı   | Geri/ileri yanında ana sayfa kısayolu                 |
|                          | İleri                        | **Açık** | Geri düğmesinin yanında ileri düğmesi                 |
|                          | Yer İşareti Ekle             | **Açık** | Hızlı yer imi ekleme                                  |
|                          | Bölünmüş görünümde aç        | Kapalı   | Sekmeyi yan yana bölünmüş görünümde açar              |
|                          | Yeni Kişisel Pencere         | **Açık** | Gizli pencere kısayolu                                |
|                          | Kenar Çubuğu                 | Kapalı   | Yan panel açma düğmesi; kenar çubuğu zaten kapalı     |
|                          | Sekme Araması                | Kapalı   | Açık sekmeler arasında arama                          |
|                          | Cüzdan                       | Kapalı   | Brave Wallet kısayolu                                 |
|                          | Leo YZ                       | Kapalı   | Yerleşik yapay zeka asistanı düğmesi                  |
|                          | VPN                          | Kapalı   | Brave VPN kısayolu; abonelik yoksa gereksiz           |
| **Araç çubuğu**          | Şifre Yöneticisi             | Kapalı   | Yerleşik şifre yöneticisi paneli                      |
|                          | Yer İşaretleri Paneli        | Kapalı   | Yer imlerini yan panelde gösterir                     |
|                          | Okuma Listesi                | Kapalı   | Daha sonra oku listesi                                |
|                          | İndirilenler                 | Kapalı   | İndirme geçmişi paneli                                |
|                          | Tarama Verilerini Sil        | Kapalı   | Geçmiş/çerez temizleme kısayolu                       |
| **Araçlar ve işlemler**  | Yazdır                       | Kapalı   | Yazdırma iletişim kutusu                              |
|                          | QR Kodu Oluştur              | Kapalı   | Geçerli sayfa için QR kod                             |
|                          | Yayınla                      | Kapalı   | Chromecast / ekran yansıtma                           |
|                          | Bağlantıyı Kopyala           | Kapalı   | Geçerli URL'yi panoya kopyalar                        |
|                          | Cihazlarınıza gönderin       | Kapalı   | Sync ile diğer cihaza sekme gönderme                  |
|                          | Görev Yöneticisi             | Kapalı   | Sekme/process bellek kullanımı                        |
|                          | Geliştirici Araçları         | Kapalı   | DevTools kısayolu; `Cmd + Option + I` ile açılabilir  |


#### Yer imleri

- **Yer işaretleri çubuğunu göster:** **Yalnızca yeni sekme sayfasında** - günlük gezinmede üst çubuk sade kalır, yeni sekmede yer imlerine erişilir
- **Sekme gruplarını yer işareti çubuğunda göster:** **Açık**; gruplu sekmeler yer imleri çubuğunda görünür
- **Herhangi bir cihazda oluşturulan yeni sekme gruplarını yer işareti çubuğuna otomatik olarak sabitle:** **Açık**; Sync kullanıyorsan gruplar cihazlar arası yer imlerine yansır

#### Adres çubuğu


| Ayar                                                       | Önerilen | Açıklama                                                      |
| ---------------------------------------------------------- | -------- | ------------------------------------------------------------- |
| **Adres çubuğunda otomatik tamamlamayı göster**            | **Açık** | Yazarken adres, arama ve komut önerileri listelenir           |
| **Geniş adres çubuğu kullan**                              | Kapalı   | Standart genişlik yeterli; üst çubukta daha fazla alan kalır  |
| **Her zaman tam URL'yi göster**                            | Kapalı   | Adres çubuğunda kısaltılmış URL gösterilir; daha sade görünüm |
| **Tam ekranda araç çubuğunu her zaman göster**             | **Açık** | Tam ekranda üst çubuk gizlenmez; geri/ileri ve adres çubuğu kalır |
| **Ana içerik alanlarında yuvarlatılmış köşeleri gösterme** | **Açık** | Sayfa içeriği daha düz/keskin köşeli görünür                  |


**Otomatik tamamlama kaynakları** (üst seçenek açıkken):


| Kaynak                        | Önerilen | Açıklama                                                  |
| ----------------------------- | -------- | --------------------------------------------------------- |
| **Cihaz üzerindeki öneriler** | **Açık** | Yerel arama ve sık kullanılan adresler                    |
| **Gözatma geçmişi**           | **Açık** | Daha önce ziyaret ettiğin siteler                         |
| **Yer imleri**                | **Açık** | Kayıtlı yer imlerinden eşleşme                            |
| **Hızlı komutlar**            | **Açık** | Ayarlar, geçmiş, indirilenler gibi `brave://` kısayolları |
| **Leo YZ Asistanı**           | Kapalı   | Adres çubuğu önerilerinde Leo yapay zeka asistanı         |


**Adres çubuğu düğmeleri** (özelleştirme paneli → Adres çubuğu):


| Düğme                  | Önerilen | Açıklama                                           |
| ---------------------- | -------- | -------------------------------------------------- |
| **Ödüller**            | **Açık** | Brave Rewards simgesi; BAT kazanımı ve ayarları    |
| **RSS beslemesi ekle** | **Açık** | Sayfada RSS varsa abone olma kısayolu              |
| **Paylaşım Menüsü**    | **Açık** | Sayfayı paylaşma seçenekleri                       |
| **Uygulamayı yükle**   | **Açık** | PWA destekleyen sitelerde uygulama olarak kurma  |


#### Sekmeler


| Ayar                                                           | Önerilen   | Açıklama                                                  |
| -------------------------------------------------------------- | ---------- | --------------------------------------------------------- |
| **Dikey sekmeleri kullan**                                     | Kapalı     | Klasik yatay sekme şeridi                                 |
| **Sekme hoparlör simgelerinden sessize alma işlevini devre dışı bırak** | Kapalı | Kapalıyken hoparlör simgesine tıklayınca sessize alma çalışır |
| **Sekme kapatma düğmesini her zaman gizle**                    | Kapalı     | Sekmeler daha sade; kapatmak için orta tık veya `Cmd + W` |
| **Sekmeleri kapatmak için orta düğme tıklamasına izin ver**    | **Açık**   | Fare tekerleği tıklayınca sekme kapanır                   |
| **Kaydırılabilir sekme şeridini kullan**                       | Kapalı     | Çok sekme olunca küçülür; kaydırma yerine sıkıştırma      |
| **Sekme vurgulama modu**                                       | Kart       | Sekmenin üzerine gelince kart önizlemesi                  |
| **Sekme önizleme bilgi kutucuğunda bellek kullanımını göster** | **Açık**   | Hangi sekmenin RAM tükettiğini görürsün                   |
| **Etkin olmayan sekmelerin görünümü**                          | **Açık**   | Pasif sekmelerin simgesi etrafında noktalı daire          |


#### Kenar çubuğu

- **Kenar çubuğunu göster:** **Hiçbir Zaman** - yan panel kapalı, ekran alanı geniş kalır
- **Konum:** **Sağda göster** (açık olsaydı sol veya sağ seçilebilir)

---

### İçerik

**Ayarlar yolu:** `brave://settings/content`

Sayfa görüntüleme, sekme gezinme ve okuma deneyimi ayarları.

#### Genel


| Ayar                                                         | Önerilen            | Açıklama                                                          |
| ------------------------------------------------------------ | ------------------- | ----------------------------------------------------------------- |
| **Yazı tipi boyutu**                                         | **Orta (Önerilir)** | Varsayılan okuma boyutu; çoğu site için dengeli                   |
| **Sayfa yakınlaştırma**                                      | **%100**            | Standart ölçek; site düzeni bozulmaz                              |
| **Ctrl-Tab ile en son kullanılan sekmeler arasında gezinin** | Kapalı              | `Cmd + Tab` klasik sekme sırasını takip eder                      |
| **404 sayfalarında Wayback Machine istemini göster**         | **Açık**            | Sayfa kaldırıldıysa Internet Archive'dan eski sürümü açma teklifi |


#### Speedreader


| Ayar                                                       | Önerilen | Açıklama                                                   |
| ---------------------------------------------------------- | -------- | ---------------------------------------------------------- |
| **Speedreader**                                            | **Açık** | Makale sayfalarını sade, reklamsız okuma görünümüne alır   |
| **Mümkün olduğunda Hızlı Okuma'yı otomatik olarak kullan** | **Açık** | Uygun sayfalarda elle tıklamadan Speedreader devreye girer |


> 💡 **İpucu:** Speedreader bazı sitelerde düzeni bozabilir; o sayfada aslan simgesinden veya adres çubuğundan normal görünüme dönebilirsin.

---

### Kalkanlar

**Ayarlar yolu:** `brave://settings/shields`

Brave'in temel farkı Shields'tır: reklam, izleyici ve parmak izi koruması buradan yönetilir. Buradaki ayarlar **tüm siteler için varsayılandır**; tek bir site bozulursa adres çubuğundaki aslan simgesinden siteye özel gevşetme yap.

#### Varsayılan koruma


| Ayar                                                                 | Önerilen                             | Açıklama                                                                     |
| -------------------------------------------------------------------- | ------------------------------------ | ---------------------------------------------------------------------------- |
| **Engellenen öğelerin sayısını Kalkanlar ikonunda göster**           | **Açık**                             | Aslan simgesinde kaç reklam/izleyici engellendiğini görürsün                 |
| **İzleyiciler ve reklam engelleme**                                  | **Standart**                         | Dengeli koruma; çoğu site çalışır, gereksiz reklamlar kesilir                |
| **Bağlantıları HTTPS'e yükselt**                                     | **Katı**                             | HTTP bağlantılar mümkünse şifreli HTTPS'e zorlanır                           |
| **Script'leri engelle**                                              | Kapalı                               | Açık bırakılırsa birçok site tamamen bozulur                                 |
| **Parmak izi kontrolünü engelle**                                    | **Açık**                             | Tarayıcı parmak izi ile izlemeyi zorlaştırır                                 |
| **Çerezleri engelle**                                                | **Üçüncü taraf çerezlerini engelle** | Oturum çerezleri kalır; siteler arası izleme kısıtlanır                      |
| **Bu siteyi kapattığımda beni unut**                                 | Kapalı                               | Açık olsaydı site kapanınca çerez/veri silinirdi; site bazlı açılabilir      |
| **Gelecekteki bozuk site raporları için iletişim bilgilerini sakla** | **Açık**                             | Bozuk site bildirimi gönderirken iletişim bilgini tekrar yazmazsın           |
| **Gizli pencerede öğe engellemeye izin ver**                         | Kapalı                               | Gizli oturumda Shields engellemesi normal pencereye yansımaz                 |
| **İçerik filtreleme**                                                | **Yapılandır**                       | Ek filtre listeleri - [Listeleri filtrele](#listeleri-filtrele) bölümüne bak |


#### Listeleri filtrele

**Ayarlar yolu:** `brave://settings/shields/filters`

Shields'ın **İçerik filtreleme** menüsünden açılır. Bölge, dil ve site türüne göre ek engelleme listeleri seçersin; varsayılan Shields'a ek katman ekler.

**Önerilen (açık):**


| Filtre                                 | Liste                                       | Açıklama                                    |
| -------------------------------------- | ------------------------------------------- | ------------------------------------------- |
| **Cookie notice blocker**              | EasyList Cookie                             | "Çerezleri kabul et" banner'larını gizler   |
| **Mobile app promo blocker**           | Fanboy's Mobile Notifications               | "Uygulamayı indir" pop-up'larını engeller   |
| **YouTube Shorts blocker**             | YouTube Anti-Shorts                         | Shorts akışını / kısayollarını engeller     |
| **YouTube Playables blocker**          | Remove Youtube Playables                    | YouTube oyun (Playables) öğelerini kaldırır |
| **YouTube members-only video blocker** | Remove Youtube Members video advertisements | Üyelere özel video reklamlarını engeller    |
| **Turkish website ad blocker**         | AdGuard Turkish                             | Türkçe sitelerdeki reklamlara ek koruma     |


**Kapalı bırakılanlar (gerekmedikçe açma):**

- **Annoying distractions**, **Newsletter popup**, **Social media**, **Chat app** - bazı sitelerin düzenini bozabilir
- **AI suggestions blocker** - yapay zeka öneri kutularını hedefler
- **YouTube recommendations / autodub / end elements / thumbnail** - YouTube arayüzünü agresif şekilde değiştirir; istemiyorsan kapalı bırak
- **Tracking URL blocker**, **Paywall blocker**, **Porn blocker** - ihtiyaca göre; günlük kullanımda zorunlu değil
- **Diğer dil filtreleri** (Arapça, Bulgarca, İspanyolca vb.) - yalnızca o dillerde geziniyorsan aç
- **Experimental ad blocker** - deneysel; kararlı kullanım için kapalı bırak

> 💡 **İpucu:** Bir filtre siteyi bozarsa listeden tek tek kapat; tüm Shields'ı kapatmana gerek kalmaz.

#### Sosyal medya engelleme

Gömülü sosyal medya widget'ları izleme ve ek yükleme getirebilir.


| Ayar                                                          | Önerilen | Açıklama                                          |
| ------------------------------------------------------------- | -------- | ------------------------------------------------- |
| **Facebook ile giriş yapmaya ve gömülü gönderilere izin ver** | Kapalı   | Facebook embed ve giriş düğmeleri engellenir      |
| **Gömülü X (Twitter) tweet'lerine izin ver**                  | **Açık** | Haber/blog sitelerindeki gömülü tweet'ler görünür |
| **LinkedIn gömülü gönderilere izin ver**                      | Kapalı   | LinkedIn embed'leri engellenir                    |


> 💡 **İpucu:** Site düzgün açılmıyorsa Shields'ı tamamen kapatma. Aslan simgesinden yalnızca **İzleyiciler ve reklam engelleme** veya **Çerezler** gibi tek bir özelliği gevşet; sorun devam ederse o site için Shields'ı geçici kapat.

---

### Gizlilik ve güvenlik

**Ayarlar yolu:** `brave://settings/privacy`

Tor, izleme koruması, site izinleri ve Brave'e gönderilen veriler bu bölümde yönetilir.

#### Hızlı erişim


| Menü                        | Açıklama                                                 |
| --------------------------- | -------------------------------------------------------- |
| **Tarama verilerini sil**   | Geçmiş, çerez, önbellek ve diğer kalıntıları temizle     |
| **Güvenlik**                | Güvenli Tarama, DNS - [Güvenlik](#güvenlik) bölümüne bak |
| **Site ve Kalkan Ayarları** | Konum, kamera, bildirim, pop-up gibi site izinleri       |


#### Güvenlik

**Ayarlar yolu:** `brave://settings/security`

Gizlilik ve güvenlik → **Güvenlik** menüsünden veya doğrudan yukarıdaki adresle açılır.

**Güvenli Tarama**


| Seçenek             | Önerilen   | Açıklama                                      |
| ------------------- | ---------- | --------------------------------------------- |
| **Standart koruma** | **Seçili** | Tehlikeli site, indirme ve eklenti uyarıları  |
| **Koruma yok**      | Kullanma   | Zararlı içeriğe karşı koruma devre dışı kalır |


**Gelişmiş**


| Ayar                                      | Önerilen                        | Açıklama                                                                               |
| ----------------------------------------- | ------------------------------- | -------------------------------------------------------------------------------------- |
| **Güvenli DNS kullan**                    | **Açık**                        | DNS sorguları şifreli kanaldan gider; ziyaret ettiğin alan adları daha az sızar        |
| **DNS sağlayıcı seç**                     | **İşletim sistemi varsayılanı** | macOS sistem DNS ayarını kullanır; özel sağlayıcı (Cloudflare, Quad9 vb.) isteğe bağlı |
| **JavaScript optimizasyonu ve güvenliği** | **Açık**                        | V8 ile sayfalar hızlanır; saldırıya karşı dayanıklılık çok az düşer                    |
| **Sertifikaları yönet**                   | -                               | HTTPS sertifikalarını görüntüle ve yönet                                               |


#### Gizlilik


| Ayar                                                                 | Önerilen       | Açıklama                                                           |
| -------------------------------------------------------------------- | -------------- | ------------------------------------------------------------------ |
| **WebRTC IP kullanım politikası**                                    | **Varsayılan** | Çoğu kullanım için yeterli; sızıntı sorunu yaşarsan sıkılaştır     |
| **Anında mesajlaşma için Google hizmetlerini kullanın**              | Kapalı         | Google hizmetlerine gereksiz bağlantıyı keser                      |
| **AMP sayfalarını otomatik yönlendir**                               | **Açık**       | Google AMP yerine yayıncının asıl sayfasına gider                  |
| **İzleme URL'lerini otomatik olarak yönlendir**                      | **Açık**       | Tıklama izleme parametrelerini içeren yönlendirme URL'lerini atlar |
| **Sitelerin dil tercihlerime göre parmak izimi çıkarmasını engelle** | **Açık**       | Dil listenden izleme bilgisi sızmasını azaltır                     |
| **"Do Not Track" isteği gönder**                                     | Kapalı         | Çoğu site yok sayar; ek gizlilik sağlamaz                          |


#### Tor pencereleri


| Ayar                                                       | Önerilen | Açıklama                                                 |
| ---------------------------------------------------------- | -------- | -------------------------------------------------------- |
| **Tor ile özel pencere**                                   | **Açık** | Menüden Tor üzerinden gizli gezinme kullanılabilir       |
| **.onion adreslerini yalnızca Tor pencerelerinde çözümle** | **Açık** | Onion siteler yalnızca Tor oturumunda açılır             |
| **Tor ağına bağlanmak için gönüllü ol (Snowflake)**        | Kapalı   | Bant genişliğini paylaşır; ihtiyaç yoksa kapalı bırak    |
| **Köprüleri kullan**                                       | Kapalı   | Tor engellenen ağlarda gerekir; normal kullanımda kapalı |


> Tor penceresi normal gizli pencereden daha yavaştır; yalnızca ekstra anonimlik gerektiğinde kullan.

#### Veri toplama


| Ayar                                                 | Önerilen | Açıklama                                                     |
| ---------------------------------------------------- | -------- | ------------------------------------------------------------ |
| **Gizlilik korumalı ürün analizine izin ver (P3A)**  | Kapalı   | Anonim kullanım istatistiği Brave'e gitmez                   |
| **Günlük kullanım ping'ini Brave'e otomatik gönder** | **Açık** | Aktif kullanıcı sayısı tahmini için minimal ping             |
| **Tanı raporlarını otomatik gönder**                 | **Açık** | Çökme/donma raporları kararlılık iyileştirmesine yardım eder |
| **Anket Panelisti**                                  | -        | İsteğe bağlı anket katılımı; zorunlu değil                   |


#### Güvenlik kontrolü

Brave ara ara **Güvenlik Kontrolü** önerisi gösterir (izinler, güncelleme, şifre sızıntısı vb.). **Güvenlik Kontrolü'ne git** ile incele; özellikle site izinleri birikmişse temizle.

Tarayıcı karşılaştırması için [PrivacyTests.org](https://privacytests.org/) kullanılabilir.

---

### Sync (Brave Sync)

**Ayarlar yolu:** `brave://settings/braveSync`

**Brave Sync**, yer imleri, geçmiş, şifreler, açık sekmeler, uzantılar ve ayarları cihazlar arasında senkronize eder. Google veya başka bir hesap gerekmez; veriler **uçtan uca şifreli** aktarılır ve yalnızca senin belirlediğin parola / kurtarma kodu ile okunabilir.

**Kurulum:**

1. `brave://settings/braveSync` adresine git (veya Ayarlar → **Sync**)
2. **Yeni sync zinciri başlat** veya mevcut zincire **Katıl**
3. Güçlü bir **sync parolası** belirle; kurtarma kodunu güvenli bir yere kaydet
4. Senkronize edilecek verileri seç (yer imleri, geçmiş, şifreler vb.)
5. Diğer cihazda aynı adımları tekrarla; **Katıl** seçeneğiyle aynı sync kodunu ve parolayı gir

> ⚠️ Sync parolasını veya kurtarma kodunu kaybedersen verilere erişim kurtarılamaz. Brave sunucularında şifreli veri tutulur; anahtar yalnızca sende kalır.

---

### Arama motoru

**Ayarlar yolu:** `brave://settings/search`

Adres çubuğundaki aramalar varsayılan motora gider. Normal ve gizli pencere için ayrı motor seçilebilir.

#### Varsayılan motor


| Pencere            | Önerilen   | Açıklama                                                                                |
| ------------------ | ---------- | --------------------------------------------------------------------------------------- |
| **Normal pencere** | **Google** | Adres çubuğu aramaları bu motora gider; **Değiştir** ile DuckDuckGo, Bing vb. seç       |
| **Özel pencere**   | **Google** | Gizli pencerede ayrı motor tanımlanabilir; normal pencereden farklı seçmek isteğe bağlı |


**Motor değiştirme:** İlgili satırdaki **Değiştir** → listeden motor seç.

**Özel motor ekleme:** **Arama motorlarını ve site aramalarını yönetin** → **Ekle** → ad, kısayol kelimesi ve arama URL'si (`%s` = sorgu).

#### Diğer ayarlar


| Ayar                            | Önerilen | Açıklama                                                                                                                    |
| ------------------------------- | -------- | --------------------------------------------------------------------------------------------------------------------------- |
| **Arama önerilerini iyileştir** | **Açık** | Yazdıkların varsayılan arama motoruna gider; daha iyi öneri gelir. Gizli pencerede zaten yalnızca yerel öneriler kullanılır |
| **Web Keşif Projesi**           | **Açık** | Anonim arama/tarayıcı verisi paylaşımı; kapatırsan hiçbir veri gönderilmez                                                  |


> 💡 **İpucu:** Adres çubuğunda belirli bir motoru tek seferlik kullanmak için kısayol kelimesi yazıp `Tab`'a bas (ör. tanımlı kısayol + arama terimi).

---

### Uzantılar

**Ayarlar yolu:** `brave://settings/extensions`

Brave Shields ile birlikte hangi eklentilerin çalışacağını ve tarayıcı düzeyindeki uzantı izinlerini buradan yönetirsin. Önerilen eklenti listesi: [chrome-extensions/README.md](chrome-extensions/README.md)

#### Genel ayarlar


| Ayar                                                 | Önerilen | Açıklama                                                          |
| ---------------------------------------------------- | -------- | ----------------------------------------------------------------- |
| **Uzantılar için Google ile oturum açmaya izin ver** | **Açık** | Google hesabı gerektiren eklentiler çalışabilir                   |
| **Media Router**                                     | Kapalı   | Tarayıcı içi yayın (cast) devre dışı; kullanmıyorsan kapalı bırak |
| **Widevine**                                         | **Açık** | Netflix, Spotify vb. DRM korumalı içerik için gerekli             |


**Hızlı erişim:**


| Menü                       | Yol / işlev                                            |
| -------------------------- | ------------------------------------------------------ |
| **Uzantıları yönet**       | `brave://extensions` - yükle, kaldır, izin ver         |
| **Klavye kısayolları**     | Eklenti kısayollarını özelleştir                       |
| **İnternet Mağazasını aç** | [Chrome Web Store](https://chromewebstore.google.com/) |


#### Manifest V2 uzantıları

Chrome Web Store Manifest V2'yi kaldırsa bile Brave seçili MV2 eklentilerini kendi sunucularında barındırır. İçerik Brave tarafından denetlenmez; resmi eklenti sayfasından bilgi al.

**uBlock Origin (tam sürüm) kurulumu:**

1. `brave://settings/extensions/v2` adresine git
2. **uBlock Origin'i etkinleştir** anahtarını aç
3. Gerekirse [Chrome Web Store - uBlock Origin](https://chromewebstore.google.com/detail/ublock-origin/cjpalhdlnbpafiamejdnhcphjbkeiagm) üzerinden kurulumu tamamla


| Eklenti           | Önerilen | Açıklama                                                                                                               |
| ----------------- | -------- | ---------------------------------------------------------------------------------------------------------------------- |
| **NoScript**      | Kapalı   | Sayfa bazlı script engelleme; Shields ile birlikte çoğu kullanıcı için gereksiz                                        |
| **uBlock Origin** | **Açık** | Güçlü reklam/izleyici engelleme - rehber: [uBlock Origin](chrome-extensions/Güvenlik%20ve%20Gizlilik/uBlock-Origin.md) |
| **uMatrix**       | Kapalı   | uBlock Origin ile birlikte genelde fazla katman                                                                        |
| **AdGuard**       | Kapalı   | Shields + uBlock yeterliyse ek AdGuard gerekmez                                                                        |


> 💡 **İpucu:** uBlock Origin + Shields birlikteyken bazı siteler aşırı engellenebilir. Sorun olursa önce Shields'ı gevşet veya uBlock'da siteye özel kural ekle; ikisini birden tamamen kapatma.

---

### Erişilebilirlik

**Ayarlar yolu:** `brave://settings/accessibility`

Klavye gezinme, kaydırma hareketleri ve kopyalama geri bildirimi ayarları.


| Ayar                                               | Önerilen | Açıklama                                                                |
| -------------------------------------------------- | -------- | ----------------------------------------------------------------------- |
| **Odaklanılmış nesnede kısa bir vurgulama göster** | Kapalı   | Tab ile gezinirken mavi odak halkası; ihtiyaç yoksa kapalı bırak        |
| **Sayfalarda metin imleciyle gezin**               | Kapalı   | Caret browsing; `F7` ile açılıp kapatılır. Klavye ile metin seçimi için |
| **Sayfalar arasında kaydırma**                     | **Açık** | Kaydırma hareketiyle geri/ileri gitme (touchpad veya fare)              |
| **Panoya kopyalanma onayları**                     | **Açık** | Bağlantı, resim veya video kopyalandığında kısa onay mesajı             |


**Erişilebilirlik özellikleri ekle:** [Chrome Web Store](https://chromewebstore.google.com/) üzerinden ek eklenti kurulabilir.

---

### Sistem

**Ayarlar yolu:** `brave://settings/system`

Donanım hızlandırma, pencere kapatma davranışı, bellek ve pil yönetimi ayarları.


| Ayar                                                                 | Önerilen | Açıklama                                                                 |
| -------------------------------------------------------------------- | -------- | ------------------------------------------------------------------------ |
| **Kısayollar**                                                       | -        | Brave ve eklenti klavye kısayollarını yönet                              |
| **Kullanılabilir olduğunda grafik hızlandırmayı kullan**             | **Açık** | GPU ile sayfa çizimi; macOS'ta genelde açık bırak. Siyah ekran veya takılma olursa kapat |
| **Bilgisayarınızın proxy ayarlarını açın**                           | -        | Sistem Ayarları → Ağ → … → Proksiler'e gider                             |
| **Son sekmeyi kapatırken pencereyi kapatın**                         | Kapalı   | Kapalıyken son sekme kapanınca yeni boş sekme açılır; pencere kapanmaz |
| **Çok sayıda sekmesi olan pencereleri kapatırken beni uyar**        | Kapalı   | Açık olsaydı çok sekme içeren pencere kapatılırken onay sorardı          |
| **⌘Q ile çıkmadan önce uyarı göster**                                | **Açık** | Yanlışlıkla tüm Brave'i kapatmayı önler                                  |
| **Çıkmak için Esc'ye basılması gerektiğini söyleyen tam ekran hatırlatıcısını göster** | **Açık** | Tam ekranda kısa hatırlatma gösterir                                     |


#### Bellek

Brave, etkin olmayan sekmelerin belleğini boşaltarak aktif sekmelere ve diğer uygulamalara daha fazla kaynak verir. Etkin olmayan sekmelere geri döndüğünde otomatik yeniden yüklenir.


| Ayar                                | Önerilen | Açıklama                                                                 |
| ----------------------------------- | -------- | ------------------------------------------------------------------------ |
| **Bellek Tasarrufu**                | Kapalı   | Açıkken pasif sekmeler uyutulur; geri dönüşte yeniden yükleme gecikmesi olabilir |
| **Her zaman etkin kalacak siteler** | -        | Yalnızca Bellek Tasarrufu açıkken anlamlı; eklenen siteler uyutulmaz. Kapalıyken liste boş kalabilir |


> Bellek Tasarrufu'nu açarsan video ve müzik akışı için `www.youtube.com` gibi siteleri **Her zaman etkin kalacak siteler** listesine ekle.

#### Güç

Brave, arka plan etkinliğini ve görsel efektleri (ör. kolay kaydırma, video kare hızı) sınırlandırarak pil gücünden tasarruf eder.


| Ayar                                                       | Önerilen               | Açıklama                                         |
| ---------------------------------------------------------- | ---------------------- | ------------------------------------------------ |
| **Enerji Tasarrufu**                                       | **Açık**               | Pil düşükken arka plan ve görsel efektleri kısar |
| **Yalnızca şarjı %20 veya daha azken etkinleştir**         | **Seçili**             | Yalnızca kritik pil seviyesinde devreye girer    |
| **Bilgisayarım fişe takılı değilken etkinleştir**         | Kapalı                 | Fişten çekildiğinde sürekli enerji tasarrufu; günlük kullanımda gerekmez |


#### Brave VPN

Abonelik yoksa bu ayarlar etkisiz kalır.


| Ayar                                          | Önerilen | Açıklama                                            |
| --------------------------------------------- | -------- | --------------------------------------------------- |
| **Brave VPN'de WireGuard protokolü kullanın** | Kapalı   | WireGuard veya varsayılan protokol tercihine göre   |
| **VPN tepsi simgesini göster**                | Kapalı   | Menü çubuğunda VPN simgesi; kullanmıyorsan gereksiz |


---

## ⚠️ Bilinen Sorunlar ve Çözümleri


| Sorun                                            | Neden Olur                              | Çözüm                                                                |
| ------------------------------------------------ | --------------------------------------- | -------------------------------------------------------------------- |
| Site düzgün açılmıyor / boş sayfa                | Agresif Shields veya izleyici engelleme | Aslan simgesinden Shields'ı geçici kapat veya site için istisna ekle |
| Oturum açma / ödeme hatası                       | Üçüncü taraf çerez veya script engeli   | Shields'ı o site için gevşet; gerekirse `brave://settings/shields`   |
| uBlock Origin + Shields çakışması                | Çift reklam engelleme                   | uBlock'u kullanıyorsan Shields reklam engellemesini kapatmayı dene   |
| Video reklamları hâlâ görünüyor                  | Site first-party reklam kullanıyor      | Shields ayarını kontrol et; bazı siteler tam engellenmeyebilir       |
| Eklenti Chrome'da çalışıyor, Brave'de çalışmıyor | Manifest sürümü veya izin               | `brave://extensions` → eklenti ayrıntıları; Brave sürümünü güncelle  |


---

## 🔗 Faydalı Bağlantılar

- 🌐 [Resmi Web Sitesi](https://brave.com/)
- 💾 [İndirme Sayfası](https://brave.com/download/)
- 🔒 [PrivacyTests.org - Tarayıcı gizlilik testleri](https://privacytests.org/)
- 📖 [Yardım Merkezi](https://support.brave.com/)
- 🔄 [Brave Sync yardımı](https://support.brave.com/hc/en-us/articles/15112645150091)
- 🗣️ [Topluluk](https://community.brave.app/)
- 🧩 [Chrome Eklentileri Koleksiyonu](chrome-extensions/README.md)
- 📦 [Homebrew Cask](https://formulae.brew.sh/cask/brave-browser)

---

## 📝 Notlar

> Brave, Chrome'dan geçiş için pratik bir seçenektir: eklentilerin çoğu çalışır, Shields ekstra reklam ve izleme koruması sağlar. Gizlilik karşılaştırması için [PrivacyTests.org](https://privacytests.org/) kullanılabilir.

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
