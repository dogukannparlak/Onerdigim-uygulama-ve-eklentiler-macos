# Önerdiğim Uygulama ve Eklentiler-macOS

> macOS, tarayıcı ve günlük kullanım için özenle seçilmiş uygulama ve eklenti rehberleri — kurulum, ayar ve kullanım adımlarıyla birlikte.

macOS · Chrome / Edge / Brave · Homebrew · Ücretsiz seçenekler ağırlıklı · Bilgilendirme amaçlı

---

## Genel Bakış

Bu repository, kişisel kullanım için seçtiğim uygulama ve eklentilerin son kullanıcı rehberlerini içerir. Her rehberde kurulum yöntemleri (Homebrew ve resmi indirme), önerilen ayarlar, temel kullanım ve bilinen sorunlar yer alır; mümkün olduğunca resmi kaynaklara yönlendirilir.


| Koleksiyon             | İçerik                 |
| ---------------------- | ---------------------- |
| **Uygulamalar**        | 23 rehber · 7 kategori |
| **Chrome eklentileri** | 21 rehber · 6 kategori |


---

## Depo Yapısı

```
Onerdigim-uygulama-ve-eklentiler-macos/
│
├── Kurulum ve Paket Yönetimi/
│   ├── Homebrew.md
│   └── Applite.md
│
├── Üretkenlik/
│   ├── Raycast.md
│   ├── Maccy.md
│   └── MacSai.md
│
├── Pencere ve Masaüstü/
│   ├── AltTab.md
│   ├── DockDoor.md
│   ├── DynamicNotch.md
│   ├── Rectangle.md
│   └── MiddleClick.md
│
├── Ekran Yönetimi/
│   ├── BetterDisplay.md
│   └── MonitorControl.md
│
├── Sistem Bakımı/
│   ├── AppCleaner.md
│   ├── ClearDisk.md
│   ├── Latest.md
│   ├── OnyX.md
│   ├── Mos.md
│   └── Thaw.md
│
├── Tarayıcılar/
│   └── Brave.md
│
├── Medya ve Dosya/
│   ├── VLC.md
│   ├── Stremio.md
│   ├── PeaZip.md
│   └── QBittorrent.md
│
├── chrome-extensions/
│   ├── Gizlilik ve Güvenlik/
│   ├── Görünüm Ve Okuma/
│   ├── Medya/
│   ├── YouTube/
│   ├── Steam ve Oyun/
│   ├── Web Araçları/
│   └── README.md
│
├── TEMPLATE.md
└── README.md
```

---

## Uygulamalar

### Kurulum ve Paket Yönetimi

macOS'ta yazılım kurulumu ve güncelleme altyapısı.


| Uygulama                | Ne işe yarar                                                                |
| ----------------------- | --------------------------------------------------------------------------- |
| [Homebrew](Homebrew.md) | CLI araçları ve masaüstü uygulamaları için komut satırı paket yöneticisi    |
| [Applite](Applite.md)   | Homebrew Cask uygulamalarını grafik arayüzden kurma, güncelleme ve kaldırma |


### Üretkenlik

Klavye odaklı iş akışı, pano ve sistem bakım araçları.


| Uygulama              | Ne işe yarar                                                                |
| --------------------- | --------------------------------------------------------------------------- |
| [Raycast](Raycast.md) | Klavye odaklı başlatıcı; uygulama açma, pano, snippet ve eklenti ekosistemi |
| [Maccy](Maccy.md)     | Hafif, klavye odaklı pano geçmişi yöneticisi                                |
| [Mac Sai](MacSai.md)  | Disk temizliği, malware tarama ve uygulama kaldırma                         |


### Pencere ve Masaüstü

Pencere düzeni, geçiş ve menü çubuğu / notch özelleştirme.


| Uygulama                        | Ne işe yarar                                                           |
| ------------------------------- | ---------------------------------------------------------------------- |
| [AltTab](AltTab.md)             | Windows tarzı pencere geçişi ve küçük resim önizlemeleri               |
| [DockDoor](DockDoor.md)         | Dock'ta canlı pencere önizlemeleri ve `Option + Tab` geçişi            |
| [DynamicNotch](DynamicNotch.md) | Notch'u medya, indirme ve sistem olayları için canlı yüzeye dönüştürme |
| [Rectangle](Rectangle.md)       | Klavye kısayolları ve sürükle-bırak ile pencere boyutlandırma          |
| [MiddleClick](MiddleClick.md)   | Trackpad ve Magic Mouse'ta orta tık simülasyonu                        |


### Ekran Yönetimi

Çoklu monitör, parlaklık ve HiDPI ayarları.


| Uygulama                            | Ne işe yarar                                                       |
| ----------------------------------- | ------------------------------------------------------------------ |
| [BetterDisplay](BetterDisplay.md)   | HiDPI ölçekleme, çözünürlük, XDR parlaklık ve sanal ekran yönetimi |
| [MonitorControl](MonitorControl.md) | Harici monitör parlaklık, ses ve kontrast kontrolü                 |


### Sistem Bakımı

Temizlik, bakım, güncelleme ve menü çubuğu / fare ayarları.


| Uygulama                    | Ne işe yarar                                                     |
| --------------------------- | ---------------------------------------------------------------- |
| [AppCleaner](AppCleaner.md) | Uygulamayı tercih ve önbellek dosyalarıyla birlikte tam kaldırma |
| [ClearDisk](ClearDisk.md)   | Geliştirici önbelleklerini tarayıp güvenli disk temizliği        |
| [Latest](Latest.md)         | Mac'teki uygulama güncellemelerini tek yerden kontrol            |
| [OnyX](OnyX.md)             | macOS bakım, disk doğrulama ve Finder / Dock ince ayarları       |
| [Mos](Mos.md)               | Harici fare kaydırmayı trackpad kalitesinde pürüzsüzleştirme     |
| [Thaw](Thaw.md)             | Menü çubuğu simgelerini gizleme, düzenleme ve notch desteği      |


### Tarayıcılar

Tarayıcı kurulum ve ayar rehberleri.


| Uygulama          | Ne işe yarar                                                            |
| ----------------- | ----------------------------------------------------------------------- |
| [Brave](Brave.md) | Gizlilik odaklı Chromium tarayıcı; yerleşik reklam / izleyici engelleme |


### Medya ve Dosya

Video, arşiv ve indirme araçları.


| Uygulama                      | Ne işe yarar                                       |
| ----------------------------- | -------------------------------------------------- |
| [VLC](VLC.md)                 | Çok formatlı medya oynatıcı                        |
| [Stremio](Stremio.md)         | Film / dizi izleme merkezi                         |
| [PeaZip](PeaZip.md)           | 200+ arşiv formatını açma, sıkıştırma ve şifreleme |
| [qBittorrent](QBittorrent.md) | Açık kaynak torrent istemcisi                      |


---

## Chrome Eklentileri

Chrome, Edge ve Brave için eklenti rehberleri. Tam liste: [chrome-extensions/README.md](chrome-extensions/README.md)

### Gizlilik ve Güvenlik


| Eklenti                                                                                                     | Ne işe yarar                                                     |
| ----------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------- |
| [AdBlock](chrome-extensions/Gizlilik%20ve%20Gu%CC%88venlik/AdBlock.md)                                      | Reklam, pop-up ve izleyici engelleme                             |
| [uBlock Origin](chrome-extensions/Gizlilik%20ve%20Gu%CC%88venlik/uBlock-Origin.md)                          | Açık kaynak reklam ve izleyici engelleyici; Brave'de MV2 desteği |
| [I don't care about cookies](chrome-extensions/Gizlilik%20ve%20Gu%CC%88venlik/I-dont-care-about-cookies.md) | Çerez onay pencerelerini otomatik kapatma                        |
| [Buster: Captcha Solver](chrome-extensions/Gizlilik%20ve%20Gu%CC%88venlik/Buster-Captcha-Solver.md)         | reCAPTCHA sesli doğrulamalarını otomatik çözme                   |


### Görünüm Ve Okuma


| Eklenti                                                                                 | Ne işe yarar                                |
| --------------------------------------------------------------------------------------- | ------------------------------------------- |
| [Dark Reader](chrome-extensions/G%C3%B6r%C3%BCn%C3%BCm%20Ve%20Okuma/Dark-Reader.md)     | Tüm sitelerde otomatik karanlık mod         |
| [Medium Parser](chrome-extensions/G%C3%B6r%C3%BCn%C3%BCm%20Ve%20Okuma/Medium-Parser.md) | Medium ücretli makalelere alternatif erişim |


### Medya


| Eklenti                                                                   | Ne işe yarar                           |
| ------------------------------------------------------------------------- | -------------------------------------- |
| [GoFullPage](chrome-extensions/Medya/GoFullPage.md)                       | Tam sayfa ekran görüntüsü              |
| [Hover Zoom+](chrome-extensions/Medya/Hover-Zoom%2B.md)                   | Fare ile resim / video büyütme         |
| [Resim içinde Resim (PiP)](chrome-extensions/Medya/Picture-in-Picture.md) | Kayan PiP penceresinde video izleme    |
| [Save image as Type](chrome-extensions/Medya/Save-image-as-Type.md)       | Resmi PNG / JPG / WebP olarak kaydetme |
| [Volume Master](chrome-extensions/Medya/Volume-Master.md)                 | Sekme bazlı ses kontrolü ve yükseltme  |


### YouTube


| Eklenti                                                                                           | Ne işe yarar                                     |
| ------------------------------------------------------------------------------------------------- | ------------------------------------------------ |
| [Enhancer for YouTube](chrome-extensions/YouTube/Enhancer-for-YouTube.md)                         | Oynatıcı özelleştirme, hız, tema, Shorts gizleme |
| [Multiselect for YouTube](chrome-extensions/YouTube/Multiselect-for-YouTube.md)                   | Playlist çoklu seçim ve toplu düzenleme          |
| [SponsorBlock](chrome-extensions/YouTube/SponsorBlock.md)                                         | Sponsor ve gereksiz segment atlama               |
| [Playlist Duration Calculator](chrome-extensions/YouTube/YouTube-Playlist-Duration-Calculator.md) | Playlist toplam süre hesaplama                   |


### Steam ve Oyun


| Eklenti                                                                   | Ne işe yarar                                 |
| ------------------------------------------------------------------------- | -------------------------------------------- |
| [Augmented Steam](chrome-extensions/Steam%20ve%20Oyun/Augmented-Steam.md) | Steam fiyat karşılaştırma ve kişiselleştirme |
| [Steam TRY](chrome-extensions/Steam%20ve%20Oyun/Steam-TRY.md)             | Steam fiyatlarını TL olarak gösterme         |
| [SteamDB](chrome-extensions/Steam%20ve%20Oyun/SteamDB%20.md)              | Fiyat geçmişi ve oyuncu istatistikleri       |


### Web Araçları


| Eklenti                                                                          | Ne işe yarar                                 |
| -------------------------------------------------------------------------------- | -------------------------------------------- |
| [Search by Image](chrome-extensions/Web%20Ara%C3%A7lar%C4%B1/Search-by-Image.md) | Tersine görsel arama; 30+ arama motoru       |
| [Web Archives](chrome-extensions/Web%20Ara%C3%A7lar%C4%B1/Web-Archives%20.md)    | Wayback Machine ve arşiv servislerinde arama |


---

## Nasıl Kullanılır?

1. Yukarıdaki kategoriden ihtiyacına uygun uygulamayı veya eklentiyi seç
2. İlgili `.md` dosyasını aç; kurulum ve ayar adımlarını oku
3. Yazılımı **yalnızca resmi kaynaktan** indir (Homebrew, Mac App Store, GitHub, resmi site)
4. Sistem araçlarında değişiklik yapmadan önce Time Machine veya tam yedek al

> Yeni rehber eklerken [TEMPLATE.md](TEMPLATE.md) dosyasını şablon olarak kullanabilirsin.

---

## Notlar

Rehberler kişisel kullanım ve bilgilendirme amaçlıdır; uygulama sürümleri ve arayüzler zamanla değişebilir. Güncel bilgi için her zaman resmi dokümantasyonu kontrol et.

---

## Sorumluluk Reddi

Bu repository yalnızca bilgilendirme amaçlıdır. Burada önerilen uygulamalar ve eklentiler:

- **Kendi sorumluluğunuzda kullanın** — Sisteminizde oluşabilecek sorun, veri kaybı veya hasardan sorumlu değiliz
- **Resmi kaynaklardan indirin** — Uygulamaları resmi web sitelerinden veya güvenilir kaynaklardan edinin
- **Güncellik garantisi yoktur** — Bilgiler zaman içinde güncelliğini yitirebilir
- **Virüs / malware kontrolü yapın** — İndirdiğiniz dosyaları güvenlik yazılımınızla tarayın
- **Sistem yedeklemesi alın** — Önemli verilerinizi yedeklemeden yeni yazılım kurmayın
- **Lisans koşullarına dikkat edin** — Her uygulamanın kendi lisans koşulları vardır
- **Kişisel veri güvenliği** — Uygulamaların gizlilik politikalarını inceleyin

**Kullanım öncesi mutlaka araştırma yapın ve bu uygulamaları kendi riskinizle kullanın.**

---

*Son güncelleme: 2026-06-18*