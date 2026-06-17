# 🛠️ Stremio

> **Kısa Açıklama:** Film, dizi ve canlı yayın içeriklerini eklentilerle tek arayüzde toplayan modern medya merkezi.

4.4.x · macOS (Apple Silicon / Intel) · Ücretsiz · Medya / Streaming

---

## 📌 Genel Bakış

Stremio, Netflix, YouTube, Twitch gibi farklı kaynaklardaki içerikleri tek uygulamada birleştiren bir medya toplayıcısıdır. Eklenti tabanlı çalışır; ücretsiz hesapla kütüphanen, izleme geçmişin ve eklenti ayarların tüm cihazlarda senkronize olur. iOS sürümünde eklenti desteği sınırlıdır.

---

## ✨ Öne Çıkan Özellikler

- **Eklenti sistemi** - İçerik kaynaklarını tek tıkla ekle
- **Cihazlar arası senkron** - Kütüphane ve izleme geçmişi bulutta
- **Kaldığın yerden devam** - Bölüm ve film ilerlemesi otomatik kaydedilir
- **Keşfet ve Pano** - Popüler içerikler ve yeni bölüm bildirimleri
- **Altyazı desteği** - OpenSubtitles gibi resmi eklentilerle
- **macOS uyumlu** - Apple Silicon ve Intel Mac; ayrıca Android, Android TV, web

---

## 📥 İndirme ve Kurulum

### Yöntem 1: Homebrew (Önerilen)

```bash
brew install --cask stremio
```

> Homebrew yüklü değilse: [brew.sh](https://brew.sh) adresindeki komutu Terminal'de çalıştır.

### Yöntem 2: Resmi İndirme

1. [stremio.com/downloads](https://www.stremio.com/downloads) adresine git
2. macOS sürümünü indir (.dmg)
3. Uygulamayı **Applications** klasörüne sürükle
4. Gatekeeper uyarısı çıkarsa: Sistem Ayarları → Gizlilik ve Güvenlik → Yine de Aç

---

## ⚙️ İlk Kurulum ve Önerilen Ayarlar

1. **Hesap oluştur:** Uygulamayı aç → ücretsiz hesap oluştur veya giriş yap
2. **Senkron:** Ayarlardan bulut senkronizasyonunun açık olduğunu doğrula
3. **Resmi eklentiler:** Puzzle ikonu → **Add-ons** → YouTube, OpenSubtitles, WatchHub kur
4. **Trakt (isteğe bağlı):** Trakt.tv hesabın varsa Trakt eklentisini bağla

> 💡 Eklenti kurduğunda ayarlar hesabına kaydedilir; başka cihazda giriş yapınca otomatik gelir.

---

## 🚀 Temel Kullanım

### Keşfet ve izleme

1. **Keşfet** sekmesinden film/dizi ara veya kategorilere göz at
2. İçeriğe tıkla → **Kütüphaneye ekle**
3. **Kütüphane** sekmesinden seç → oynat

### Ana ekranlar

| Sekme | İşlev |
| ----- | ----- |
| **Pano** | Devam eden diziler, yeni bölümler, öneriler |
| **Keşfet** | Arama, tür filtreleri, popüler içerikler |
| **Kütüphane** | Eklediğin film/diziler, izleme durumu |

---

## 🔌 Eklenti Ekosistemi

Stremio'nun asıl gücü eklentilerdedir. Eklentiler sunucu tarafında çalışır; tek tıkla kurulur ve hesabına senkron olur. Kurulum kolaydır; ancak üçüncü taraf sunucuların çalışır durumda olmasına bağımlısın.

### Resmi ve topluluk eklentileri

| Eklenti | İşlev | Not |
| ------- | ----- | --- |
| YouTube, Twitch, WatchHub, OpenSubtitles, FilmOn | Yasal kaynaklar | Güvenli temel |
| Torrentio, Cyberflix Catalog, USA TV | Topluluk kaynakları | Gri alan; kullanıcı sorumluluğu |

### Eklenti kurma

1. Sol üstteki **puzzle** ikonuna tıkla → **Add-ons**
2. Listeden **Install** ile kur
3. Veya yapılandırma linkini yapıştır (Torrentio gibi)

### Torrentio yapılandırma

1. [torrentio.strem.fun/configure](https://torrentio.strem.fun/configure) adresine git
2. **Sağlayıcı seç:**
   - **YTS** - Filmler, düşük boyut, 4K
   - **1337x** - Geniş içerik yelpazesi
   - **RARBG** - Yüksek kalite, güvenilir
   - **EZTV** - TV dizileri
3. **Kalite filtreleri:** 1080p / 4K tercih et; CAM ve Screener gibi düşük kaliteyi hariç tut
4. **Real-Debrid API** (isteğe bağlı) - Daha hızlı ve kararlı akış
5. Oluşan linki kopyala → Stremio **Add-ons** → yapıştır → Install

### Trakt entegrasyonu

Trakt eklentisi kurulduğunda izlediğin bölümler otomatik senkron olur (scrobbling). İzleme istatistikleri, takvim ve kişisel notlar için [Trakt.tv](https://trakt.tv) hesabı gerekir.

---

## ⚠️ Bilinen Sorunlar ve Çözümleri

| Sorun | Neden Olur | Çözüm |
| ----- | ---------- | ----- |
| Akış açılmıyor | Eklenti sunucusu kapalı | Farklı eklenti dene; Torrentio linkini yeniden oluştur |
| iOS'ta eklenti yok | Platform kısıtı | Android/PC kullan veya Chromecast ile yayın yap |
| Altyazı gelmiyor | OpenSubtitles kapalı | OpenSubtitles eklentisini kur ve etkinleştir |
| Senkron çalışmıyor | Hesap / ağ sorunu | Çıkış yap → tekrar giriş; internet bağlantısını kontrol et |

---

## 🔗 Faydalı Bağlantılar

- 🌐 [Resmi Web Sitesi](https://www.stremio.com/)
- 📥 [İndirme Sayfası](https://www.stremio.com/downloads)
- 💾 [GitHub (Web sürümü)](https://github.com/Stremio/stremio-web)
- 🔌 [Torrentio Yapılandırma](https://torrentio.strem.fun/configure)
- 📦 [Homebrew Cask](https://formulae.brew.sh/cask/stremio)
- 📺 [Trakt.tv](https://trakt.tv/)

---

## 📝 Notlar

> Stremio uygulaması ve resmi eklentiler yasal kaynaklara erişim sağlar. Topluluk eklentileri ve izlenen içeriğin kaynağı tamamen kullanıcı sorumluluğundadır; telif hakkı ihlali yasal risk doğurabilir. VPN kullanımı isteğe bağlıdır - yalnızca yasal içerik tüketmekten sorumlusun.

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

*Son güncelleme: 2026-05-22*
