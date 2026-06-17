# 🛠️ Thaw

> **Kısa Açıklama:** Menü çubuğu simgelerini gizleyip düzenleyen, notch'lu MacBook'larda ikinci bir bar sunan ve menü çubuğu görünümünü özelleştiren ücretsiz, açık kaynaklı menü çubuğu yöneticisi.

v1.2.0 · macOS 26+ (Apple Silicon / Intel) · GPL-3.0 / açık kaynak · Menü çubuğu

---

## 📌 Genel Bakış

Çok sayıda menü çubuğu uygulaması (Maccy, Mos, Rectangle, Latest…) kurulduğunda simgeler taşar; notch'lu MacBook'larda sağ taraf daralır ve simgeler üst üste biner. macOS yerleşik olarak simgeleri bölümlere ayırmayı veya sürükleyerek düzenlemeyi pratik biçimde sunmaz.

**Thaw**, [Ice](https://github.com/jordanbaird/Ice) projesinin aktif çatallanmış (fork) sürümüdür; simgeleri **gösterilen**, **gizli** ve **her zaman gizli** bölümlere ayırır, fareyle veya kısayolla geçici olarak açar, sürükle-bırak arayüzüyle düzenler ve isteğe bağlı **Thaw Bar** ile gizli simgeleri menü çubuğunun altında gösterir. Ücretli [Bartender](https://www.macbartender.com/) gibi araçlara alternatif olarak tamamen ücretsiz ve açık kaynaktır; Türkçe dahil geniş dil desteği vardır.

> Resmi gereksinim **macOS 26+**'dır. Homebrew cask en az macOS 14 bildirir; en güncel özellikler ve uyumluluk için macOS 26 kullanman önerilir.

---

## ✨ Öne Çıkan Özellikler

- **Bölüm yönetimi** — Gösterilen, gizli ve her zaman gizli menü çubuğu bölümleri
- **Geçici gösterme** — Boş alana tıklama, çift tıklama, hover veya kaydırma ile gizli simgeleri aç
- **Thaw simgesi** — Tek tıkla gizli, çift tıkla her zaman gizli, sağ tıkla ayarlar
- **Otomatik yeniden gizleme** — Akıllı algoritma veya zamanlayıcı ile simgeleri tekrar gizle
- **Sürükle-bırak düzen** — Simge sırasını görsel arayüzde ve menü çubuğunda `⌘` + sürükle ile ayarla
- **Thaw Bar** — Notch'lu MacBook'larda gizli simgeleri menü çubuğunun altında ayrı bir barda göster
- **Simge arama** — Menü çubuğu simgelerinde hızlı arama paneli
- **Profiller** — Farklı ekranlar veya kullanım senaryoları için menü çubuğu düzeni profilleri
- **Görünüm özelleştirme** — Menü çubuğu renk tonu (düz/gradyan), gölge, kenarlık, özel şekiller; açık/koyu mod ayrı ayar
- **Kısayollar** — Bölüm aç/kapa, arama paneli, Thaw Bar, uygulama menülerini gizle/göster
- **Türkçe arayüz** — Crowdin üzerinden yerelleştirilmiş
- **Tamamen ücretsiz** — Açık kaynak ([GPL-3.0](https://github.com/stonerl/Thaw/blob/development/LICENSE))

---

## 📥 İndirme ve Kurulum

### Yöntem 1: Homebrew (Önerilen)

```bash
brew install --cask thaw
```

Güncelleme:

```bash
brew update
brew upgrade --cask thaw
```

En güncel beta (veya stable — hangisi yeniyse):

```bash
brew install --cask thaw@beta
```

> Homebrew yüklü değilse: [brew.sh](https://brew.sh) adresindeki komutu Terminal'de çalıştır.

### Yöntem 2: GitHub Releases

1. [GitHub Releases](https://github.com/stonerl/Thaw/releases/latest) sayfasına git
2. `Thaw_<sürüm>.zip` dosyasını indir ve arşivi aç
3. `Thaw.app` dosyasını **Applications** klasörüne taşı
4. Gatekeeper uyarısı çıkarsa: Sistem Ayarları → Gizlilik ve Güvenlik → Yine de Aç

---

## ⚙️ Ayarlar Penceresi

Thaw simgesine **sağ tıkla** → **Ayarlar** (veya Thaw simgesine tıkla → ayarlar). Sol menüdeki sekmeler:

| Sekme | Ne işe yarar |
| ----- | ------------ |
| **Genel** | Başlangıç, Thaw simgesi, gizli simgeleri açma yöntemleri, otomatik yeniden gizleme |
| **Ekranlar** | Çoklu monitörde ekran bazlı menü çubuğu davranışı |
| **Menü Çubuğu Düzeni** | Simge bölümleri, sürükle-bırak düzen, Thaw Bar, profiller, arama |
| **Menü Çubuğu Görünümü** | Renk tonu, gölge, kenarlık, şekil; açık/koyu mod |
| **Kısayollar** | Klavye kısayolu atamaları |
| **Gelişmiş** | Bölüm ayırıcıları, ipuçları, performans, izinler |
| **Hakkında** | Sürüm, güncelleme, bağış |

---

## ⚙️ İlk Kurulum ve Önerilen Ayarlar

### 1. İzinler (Gelişmiş → İzinler)

1. Thaw'u bir kez aç; macOS izin isteyecektir
2. **Erişilebilirlik (zorunlu):** Sistem Ayarları → Gizlilik ve Güvenlik → **Erişilebilirlik** → Thaw'u etkinleştir
3. İzin verilmezse simge düzenleme ve gizleme çalışmaz; **Gelişmiş → İzinler** sekmesinden durumu kontrol et

### 2. Genel — önerilen yapılandırma

| Ayar | Öneri | Açıklama |
| ---- | ----- | -------- |
| **Oturum açıldığında başlat** | Açık | Thaw her oturumda menü çubuğunu yönetsin |
| **Thaw simgesini göster** | Açık | Thaw simgesi menü çubuğunda kalsın |
| **Thaw simgesi** | Tercihe göre | Simge stilini seç (ör. Kapı) |
| **Tıklamada göster** | Açık | Boş alana tıklayınca gizli simgeler açılır |
| **Her zaman gizli için çift tıkla** | Açık | Boş alana çift tıklayınca always-hidden bölümü açılır |
| **Üzerine gelindiğinde göster** | Kapalı | Yanlışlıkla açılmayı azaltır; tıklama + kaydırma yeterli |
| **Kaydırmada göster** | Açık | Menü çubuğunda scroll/swipe ile gizli simgeleri döngüsel göster |
| **Otomatik olarak tekrar gizle** | Açık | Geçici gösterimden sonra simgeler kapanır |
| **Strateji** | **Akıllı** | Kullanım alışkanlığına göre optimal yeniden gizleme |
| **Menü çubuğu öğesi boşluğu** (BETA) | Varsayılan | Değiştirirsen **Uygula** — tüm menü çubuğu uygulamalarını yeniden başlatır; gerekirse oturumu kapat/aç |

> 💡 Thaw simgesi davranışı: **tek tık** → gizli simgeleri göster · **çift tık** → her zaman gizli bölüm · **sağ tık** → ayarlar

### 3. Menü Çubuğu Düzeni — simgeleri böl

1. **Menü Çubuğu Düzeni** sekmesine git
2. Simge listesinde öğeleri üç bölüme sürükle:

| Bölüm | Bu repodaki örnek simgeler |
| ----- | -------------------------- |
| **Gösterilen** | Thaw, saat, pil, Wi‑Fi — sık bakılan sistem simgeleri |
| **Gizli** | Maccy, Mos, Rectangle, Latest — sık kullanılan ama sürekli görünmesi gerekmeyen araçlar |
| **Her zaman gizli** | Nadiren açılan yardımcı uygulamalar, deneme amaçlı simgeler |

3. Notch'lu MacBook'ta **Thaw Bar**'ı etkinleştir — gizli simgeler menü çubuğunun altında ayrı barda listelenir
4. İsteğe bağlı: **Profiller** ile iş / oyun / sunum modları için ayrı düzenler kaydet

> Simge sırasını menü çubuğunda da **`⌘` basılı sürükleyerek** değiştirebilirsin. **Gelişmiş**'te **⌘ + sürüklerken tüm bölümleri göster** açıksa bölümler arası taşıma daha kolay olur.

### 4. Gelişmiş — önerilen yapılandırma

| Ayar | Öneri | Açıklama |
| ---- | ----- | -------- |
| **Her zaman gizli bölümü etkinleştir** | Açık | Üçüncü bölümü kullanabilmek için gerekli |
| **⌘ + sürüklerken tüm bölümleri göster** | İsteğe bağlı | Düzenleme sırasında bölüm sınırlarını gör |
| **Bölüm ayırıcı stili** | Yok / tercihe göre | Bölümler arası görsel ayırıcı |
| **Menü çubuğunda ipuçlarını göster** | İsteğe bağlı | Simge üzerine gelince adını gösterir |
| **Menü çubuğu öğeleri gösterilirken uygulama menülerini gizle** | Kapalı | Alan kazanmak için açılabilir; Thaw'un Dock'ta görünmesi gerekir |
| **İkincil bağlam menüsünü etkinleştir** | İsteğe bağlı | Boş alana sağ tık → minimal Thaw menüsü |
| **Kısayolda fare imlecinde göster** | İsteğe bağlı | Thaw Bar kısayolla imleç konumunda açılır |
| **Üzerine gelme gecikmesi** | 0,2 sn | Hover açıksa tetikleme gecikmesi |
| **Simge yenileme hızı** | 2 fps | Animasyonlu simgeler için; CPU kullanımını etkiler |

### 5. Menü çubuğu otomatik gizleme (macOS)

Sistem Ayarları → **Kontrol Merkezi** → menü çubuğunu otomatik gizleme açıksa Thaw düzenleme yaparken hata alabilirsin. Düzenleme öncesi geçici olarak **Asla** seç, düzeni kaydet, ardından eski ayara dön — ayrıntılar Bilinen Sorunlar bölümünde.

---

## 🚀 Temel Kullanım

### Thaw simgesi ile

| Hareket | Sonuç |
| ------- | ----- |
| **Tek tık** | Gizli bölümdeki simgeleri göster |
| **Çift tık** | Her zaman gizli bölümü göster |
| **Sağ tık** | Ayarlar penceresini aç |
| **`⌥` + tık** | Her zaman gizli bölüme hızlı erişim (alternatif) |

### Menü çubuğu boş alanı ile

| Hareket | Sonuç |
| ------- | ----- |
| **Tek tık** | Gizli simgeleri göster (**Tıklamada göster** açıksa) |
| **Çift tık** | Her zaman gizli simgeleri göster |
| **Kaydırma / swipe** | Gizli simgeler arasında döngüsel geçiş |
| **Hover** | Üzerine gelince göster (**Üzerine gelindiğinde göster** açıksa) |

Gösterim bittikten sonra **Otomatik olarak tekrar gizle** + **Akıllı** strateji simgeleri kapatır.

### Simge bölümlerini düzenleme

1. **Menü Çubuğu Düzeni** sekmesini aç
2. Listeden simgeleri **Gösterilen**, **Gizli** veya **Her zaman gizli** bölümlerine sürükle
3. Veya menü çubuğunda simgeyi **`⌘` basılı tutarak sürükle**

### Kaybolan simgeyi geri getirme

Thaw simgeleri silmez; genelde **Her zaman gizli** bölümüne düşerler.

1. Thaw simgesine **çift tıkla** veya **`⌥` + tıkla** (always-hidden bölümünü aç)
2. Simgeyi **`⌘` + sürükleyerek** **Gizli** veya **Gösterilen** bölümüne taşı

### Thaw Bar (notch'lu Mac)

**Menü Çubuğu Düzeni**'nde Thaw Bar'ı etkinleştir. Gizli simgeler menü çubuğunun hemen altında yatay bir barda listelenir; notch alanı kalabalıklaşmaz. **Kısayollar** sekmesinden Thaw Bar'ı aç/kapa kısayolu atanabilir.

### Simge arama

**Kısayollar** sekmesinden arama paneli kısayolu ata. Panel açıldığında menü çubuğu simgelerini ada göre bulup etkinleştir.

### Profiller

**Menü Çubuğu Düzeni → Profiller** ile farklı düzenler kaydet — örneğin sunum modunda yalnızca sistem simgeleri görünsün, günlük kullanımda Maccy ve Mos gizli bölümde kalsın.

### Menü çubuğu görünümü

**Menü Çubuğu Görünümü** sekmesinde renk tonu (düz veya gradyan), gölge, kenarlık ve özel şekil ayarla. Açık ve koyu mod için ayrı profiller tanımlayabilirsin.

### Çoklu monitör

**Ekranlar** sekmesinden harici monitörlerde menü çubuğu davranışını ayrı yapılandır.

### Klavye kısayolları

**Kısayollar** sekmesinden atanabilir eylemler:

| Eylem | Açıklama |
| ----- | -------- |
| Bölüm aç/kapa | Gösterilen veya gizli bölümü toggle et |
| Arama paneli | Menü çubuğu simge aramasını aç |
| Thaw Bar | Alt barı etkinleştir / devre dışı bırak |
| Bölüm ayırıcı simgeleri | Ayırıcıları göster / gizle |
| Uygulama menüleri | Çakışmayı önlemek için uygulama menülerini gizle/göster |

> Tüm kısayollar **Kısayollar** sekmesinden özelleştirilir; varsayılanlar sürüme göre değişebilir.

---

## ⚠️ Bilinen Sorunlar ve Çözümleri

| Sorun | Neden Olur | Çözüm |
| ----- | ---------- | ----- |
| Simge kayboldu / Thaw kaldırdı | Simge **Her zaman gizli** bölümüne düştü | Thaw simgesine çift tıkla veya `⌥` + tıkla → simgeyi `⌘` + sürükleyerek taşı |
| Yeni simgeler always-hidden'a gidiyor | macOS yeni simgeleri sol tarafa ekler | Thaw güncel sürümde tanıdığı simgeleri geri taşır; yine de olursa **Menü Çubuğu Düzeni**'nden manuel düzenle |
| `Cannot arrange menu bar items in automatically hidden menu bars` | Menü çubuğu otomatik gizleme açık | Sistem Ayarları → Kontrol Merkezi → **Menü çubuğunu otomatik gizle ve göster** → geçici **Asla** → Thaw'ta düzeni güncelle → eski ayara dön |
| Simge sırası yeniden başlatınca bozuluyor | macOS / bazı uygulamalar konumu hatırlamaz | Sık kullanılanları **Gösterilen**'de tut; **Profiller** kullan |
| Thaw çalışmıyor / düzenlemiyor | Erişilebilirlik izni eksik veya bozulmuş | **Gelişmiş → İzinler**'i kontrol et; Thaw'u listeden kaldırıp yeniden ekle |
| Boşluk ayarı uygulanmadı | BETA özellik, oturum gerekir | **Menü çubuğu öğesi boşluğu** sonrası oturumu kapat/aç |
| Bartender / Ice ile çakışma | İki menü çubuğu yöneticisi aynı anda | Yalnızca birini aktif tut |

---

## 🔗 Faydalı Bağlantılar

- 💾 [GitHub Sayfası](https://github.com/stonerl/Thaw)
- 📦 [GitHub Releases](https://github.com/stonerl/Thaw/releases/latest)
- 📖 [Sık karşılaşılan sorunlar](https://github.com/stonerl/Thaw/blob/development/FREQUENT_ISSUES.md)
- 🗣️ [GitHub Discussions](https://github.com/stonerl/Thaw/discussions)
- 💬 [Discord](https://discord.gg/5cnKkKbMFd)
- 🌐 [Crowdin (çeviri)](https://crowdin.com/project/thaw)
- 📦 [Homebrew Cask](https://formulae.brew.sh/cask/thaw)
- 🔀 [Orijinal Ice projesi](https://github.com/jordanbaird/Ice)

---

## 📝 Notlar

> Thaw, menü çubuğu kalabalıklaşan Mac kullanıcıları için en kapsamlı ücretsiz çözümlerden biridir. Ice'dan geçiş doğrudan mümkündür; Thaw aktif geliştirme, macOS 26 uyumluluğu ve yol haritasındaki eksik özellikleri tamamlamayı hedefler. Bu repodaki menü çubuğu araçları (Maccy, Mos, Rectangle, Latest vb.) **Gizli** bölümde tutulduğunda notch alanı rahatlar; **Tıklama + kaydırma + otomatik yeniden gizleme** kombinasyonu günlük kullanım için en pratik akıştır.

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
