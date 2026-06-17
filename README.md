# Önerdiğim Uygulama ve Eklentiler (macOS)

macOS için özenle seçilmiş masaüstü uygulamaları ve tarayıcı eklentileri rehberi. Her uygulama kurulum, önerilen ayarlar ve temel kullanım adımlarıyla birlikte sunulur.

**4 uygulama** · **21 eklenti** · Kurulum: **Homebrew (Önerilen)** veya resmi `.dmg`

---

## 🍺 Homebrew

Tüm uygulamalar Homebrew Cask ile kurulabilir. Homebrew yüklü değilse:

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

Detaylar: [brew.sh](https://brew.sh)

---

## 📱 Masaüstü Uygulamaları


| Uygulama | Açıklama | Homebrew (Önerilen) | Resmi İndirme |
| -------- | -------- | ------------------- | ------------- |
| [Brave Browser](Brave.md) | Gizlilik odaklı Chromium tabanlı tarayıcı | `brew install --cask brave-browser` | [brave.com/download](https://brave.com/download/) |
| [VLC Media Player](VLC.md) | Evrensel medya oynatıcı | `brew install --cask vlc` | [videolan.org/vlc](https://www.videolan.org/vlc/) |
| [Stremio](Stremio.md) | Eklenti tabanlı medya merkezi | `brew install --cask stremio` | [stremio.com/downloads](https://www.stremio.com/downloads) |
| [qBittorrent](QBittorrent%20.md) | Reklamsız BitTorrent istemcisi | `brew install --cask qbittorrent` | [qbittorrent.org/download](https://www.qbittorrent.org/download) |

Tüm uygulamaları tek komutla kurmak için:

```bash
brew install --cask brave-browser vlc stremio qbittorrent
```

---

## 🧩 Tarayıcı Eklentileri

Brave (macOS) üzerinde önerilen Chrome eklentileri koleksiyonu:

**[Chrome Eklentileri Koleksiyonu →](chrome-extensions/README.md)**

21 eklenti · 6 kategori · Güvenlik, medya, YouTube, Steam ve daha fazlası

---

## 🚀 Nasıl Kullanılır?

1. İhtiyacına uygun uygulama veya eklenti rehberini aç
2. **Yöntem 1: Homebrew (Önerilen)** ile terminalden kur veya **Yöntem 2: Resmi Site** ile `.dmg` indir
3. Rehberdeki önerilen ayarları uygula
4. Sorun yaşarsan dosyadaki "Bilinen Sorunlar" bölümüne bak

---

## 📝 Yeni Rehber Ekleme

Yeni uygulama veya eklenti eklerken [`TEMPLATE.md`](TEMPLATE.md) şablonunu kullan.

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
