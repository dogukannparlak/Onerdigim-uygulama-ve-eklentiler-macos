# 🛠️ VLC Media Player

> **Kısa Açıklama:** Neredeyse tüm video ve ses formatlarını ek codec paketi gerektirmeden oynatan ücretsiz medya oynatıcısı.

Güncel · macOS (Apple Silicon / Intel) · Ücretsiz / açık kaynak · Medya

---

## 📌 Genel Bakış

VLC, VideoLAN tarafından geliştirilen evrensel bir medya oynatıcısıdır. MP4, MKV, AVI, MP3, FLAC ve yüzlerce formatı ek yazılım kurmadan açar. QuickTime Player veya tarayıcı oynatıcıların açamadığı dosyaları, bozuk veya yarım kalmış medyayı bile çoğu zaman oynatabilir.

---

## ✨ Öne Çıkan Özellikler

- **Evrensel format desteği** - Codec paketi gerekmez
- **Altyazı desteği** - SRT, ASS ve diğer formatlar
- **Dönüştürme** - Video/ses formatı değiştirme
- **Ağ akışı** - URL ile çevrimiçi video oynatma
- **macOS uyumlu** - Apple Silicon ve Intel Mac desteği
- **Ücretsiz** - Reklamsız, açık kaynak

---

## 📥 İndirme ve Kurulum

### Yöntem 1: Homebrew (Önerilen)

```bash
brew install --cask vlc
```

> Homebrew yüklü değilse: [brew.sh](https://brew.sh) adresindeki komutu Terminal'de çalıştır.

### Yöntem 2: Resmi İndirme

1. [videolan.org/vlc](https://www.videolan.org/vlc/) adresine git
2. **Download VLC** butonuna tıkla
3. `.dmg` dosyasını aç ve VLC'yi **Applications** klasörüne sürükle
4. Gatekeeper uyarısı çıkarsa: Sistem Ayarları → Gizlilik ve Güvenlik → Yine de Aç

---

## ⚙️ İlk Kurulum ve Önerilen Ayarlar

1. **Varsayılan oynatıcı (isteğe bağlı):** Video dosyasına sağ tık → Birlikte Aç → VLC → **Her Zaman**; veya dosyayı VLC'ye sürükle-bırak
2. **Donanım hızlandırma:** Araçlar → Tercihler → Giriş / Codecs → Donanım hızlandırmalı kod çözmeyi dene (sorun olursa kapat)
3. **Altyazı:** Araçlar → Tercihler → Altyazılar → UTF-8 kodlama
4. **Arayüz dili:** Araçlar → Tercihler → Arayüz → Dil → Türkçe

> 💡 Oynatma sorunu yaşarsan donanım hızlandırmayı kapatmak çoğu zaman işe yarar.

---

## 🚀 Temel Kullanım

### Dosya oynatma

1. VLC'yi aç → **Medya → Dosya Aç** (`Cmd + O`)
2. Veya video/ses dosyasını VLC penceresine **sürükle-bırak**
3. Çift tıkla veya Enter ile oynat

### Oynatma listesi

1. **Medya → Dosya Aç** ile birden fazla dosya seç
2. Veya **Cmd + L** ile oynatma listesi panelini aç

### Klavye kısayolları


| Kısayol     | İşlev            |
| ----------- | ---------------- |
| `Space`     | Oynat / duraklat |
| `F` / `F11` | Tam ekran        |
| `Cmd + O`  | Dosya aç         |
| `Cmd + L`  | Oynatma listesi  |
| `+` / `-`   | Ses seviyesi     |
| `[` / `]`   | Oynatma hızı     |


---

## ⚠️ Bilinen Sorunlar ve Çözümleri


| Sorun                         | Neden Olur          | Çözüm                                                  |
| ----------------------------- | ------------------- | ------------------------------------------------------ |
| Ses-görüntü senkronu bozuk    | Codec veya kaynak   | Araçlar → Senkronizasyon ile gecikmeyi ayarla          |
| Video takılıyor / siyah ekran | Donanım hızlandırma | Tercihler → Giriş/Codecs → donanım hızlandırmayı kapat |
| Altyazı bozuk karakter        | Yanlış kodlama      | Tercihler → Altyazılar → UTF-8                         |
| Ses yok                       | Yanlış ses kanalı   | Ses → Ses kanalı → Stereo veya 5.1 dene                |
| Ağ akışı açılmıyor            | URL veya protokol   | Medya → Ağ akışı aç (`Cmd + N`); URL'yi kontrol et    |


---

## 🔗 Faydalı Bağlantılar

- 🌐 [Resmi Web Sitesi](https://www.videolan.org/vlc/)
- 📖 [Desteklenen Formatlar](https://www.videolan.org/vlc/features.html)
- 📦 [Homebrew Cask](https://formulae.brew.sh/cask/vlc)
- 💾 [GitHub Sayfası](https://github.com/videolan/vlc)

---

## 📝 Notlar

> VLC çok yönlüdür ama günlük kullanımda çoğu kişi yalnızca dosya açmak için kullanır. Gelişmiş özellikler (IPTV, ekran kaydı, Chromecast) mevcuttur; ayrıntılar için resmi wiki'ye bak.

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