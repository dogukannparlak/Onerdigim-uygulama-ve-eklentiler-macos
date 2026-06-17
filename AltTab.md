# 🛠️ AltTab

> **Kısa Açıklama:** macOS'ta Windows tarzı pencere geçişi sağlayan, açık kaynaklı ve ücretsiz bir pencere yöneticisi.

v11.3 · macOS 10.13+ (Apple Silicon / Intel) · GPL-3.0 / açık kaynak · Pencere yönetimi

---

## 📌 Genel Bakış

AltTab, macOS'un yerleşik `Cmd + Tab` kısayolunun yalnızca uygulama değiştirmesi sorununu çözer; açık pencereler arasında küçük resimlerle hızlı geçiş yapmanı sağlar. Windows'tan Mac'e geçenler veya aynı uygulamanın birden fazla penceresi arasında sık geçiş yapanlar için en pratik çözümlerden biridir. Mission Control'e kıyasla daha hızlıdır; ücretsiz sürümde bile yüksek kaliteli küçük resimler, canlı önizleme ve pencere denetimleri sunar.

---

## ✨ Öne Çıkan Özellikler

*(Yalnızca ücretsiz sürüm özellikleri)*

- **Küçük resimli pencere geçişi** — Tüm açık pencereleri canlı önizlemeli küçük resimlerle listeler; güvenilir ve hızlı geçiş
- **Karanlık Mod** — macOS görünümünü (açık/koyu) otomatik izler; geçiş aracı her zaman yerel görünür
- **Canlı önizleme** — Seçili pencereyi geçiş aracından ayrılmadan tam boyutta, en üstte önizle
- **Pencere denetimleri** — Trafik ışığı simgeleriyle geçiş aracından kapat, küçült veya tam ekran yap
- **Durum rozetleri** — Hangi pencerelerin küçültülmüş, gizlenmiş veya başka bir Space'te olduğunu bir bakışta gör
- **Anında bırakma veya açık tutma** — Tuşu bırakınca hemen geç veya paneli açık tutup kendi hızında göz at
- **Özelleştirilebilir kısayol** — Neredeyse her tuş bileşimiyle kısayol tanımla; uygulama, Space veya ekrana göre süz
- **Trackpad hareketleri** — Klavyesiz tetikleme; kaydırarak pencereler arasında gezin
- **İstisnalar** — Sanal makine, uzak masaüstü veya gürültülü uygulamaları geçiş listesinden gizle
- **Erişilebilirlik** — VoiceOver, yapışkan tuşlar ve saydamlığı azaltma ile uyumlu
- **Gizlilik** — Telemetri yok, izleme yok; ağ yalnızca güncelleme denetimi ve isteğe bağlı çökme raporları için
- **Komut satırı** — `--list`, `--focus`, `--show` gibi komutlarla pencere listeleme ve odaklama
- **21 dil desteği** — Türkçe dahil tam yerelleştirme

---

## 📥 İndirme ve Kurulum

### Yöntem 1: Homebrew (Önerilen)

```bash
brew install --cask alt-tab
```

> Homebrew yüklü değilse: [brew.sh](https://brew.sh) adresindeki komutu Terminal'de çalıştır.

### Yöntem 2: Resmi İndirme

1. [alt-tab.app](https://alt-tab.app/tr/) adresine git
2. **İndir** butonuna tıkla
3. `.dmg` dosyasını aç ve AltTab'i **Applications** klasörüne sürükle
4. Gatekeeper uyarısı çıkarsa: Sistem Ayarları → Gizlilik ve Güvenlik → Yine de Aç

---

## ⚙️ İlk Kurulum ve Önerilen Ayarlar

1. **Erişilebilirlik izni (zorunlu):** İlk açılışta macOS izin ister → Sistem Ayarları → Gizlilik ve Güvenlik → Erişilebilirlik → AltTab'i etkinleştir
2. **Ekran kaydı izni (önerilen):** Küçük resimler için Sistem Ayarları → Gizlilik ve Güvenlik → Ekran ve Sistem Ses Kaydı → AltTab'i etkinleştir
3. **Girişte başlat:** Menü çubuğundaki AltTab simgesi → **Preferences** → **General** → **Launch AltTab at login**
4. **Kısayolu özelleştir (isteğe bağlı):** **Preferences → Controls** — Windows alışkanlığı için `Cmd + Tab` veya mevcut `Option + Tab`'ı koru
5. **Dil:** **Preferences → General → Language → Türkçe**

> 💡 `Cmd + Tab` zaten macOS uygulama geçişine atanmıştır. Windows'taki gibi pencere geçişi için varsayılan `Option + Tab` genelde daha az çakışma yaratır; istersen Controls sekmesinden değiştirebilirsin.

---

## 🚀 Temel Kullanım

### Pencere geçişi

1. `Option + Tab` tuşlarına bas ve **Option**'ı basılı tut
2. **Tab** ile ileri, **Shift + Tab** ile geri git (ok tuşları veya fareyle küçük resim üzerine gelme de çalışır)
3. **Option**'ı bırak, **Space**'e bas veya küçük resme tıkla — seçili pencereye geç
4. **Esc** ile geçişi iptal et

### Yalnızca aktif uygulamanın pencereleri

Varsayılan ikinci kısayol: `Option + `` (backtick / ters tırnak) — aynı uygulama içindeki pencereler arasında geçiş.

### Geçiş aracından pencere yönetimi

Küçük resmin üzerine gelince trafik ışığı simgeleri görünür; klavyeden de:

| Kısayol | İşlev |
| ------- | ----- |
| `Option + Tab` (basılı tut) | Geçiş aracını aç |
| `Tab` / `Shift + Tab` | İleri / geri |
| `Esc` | İptal |
| `Space` | Seçili pencereye geç |
| `Q` | Uygulamayı kapat |
| `W` | Pencereyi kapat |
| `M` | Küçült |
| `H` | Uygulamayı gizle |

### Komut satırı

AltTab çalışırken Terminal'den:

```bash
/Applications/AltTab.app/Contents/MacOS/AltTab --list
/Applications/AltTab.app/Contents/MacOS/AltTab --focus=window_id
/Applications/AltTab.app/Contents/MacOS/AltTab --show=shortcut_index
```

---

## ⚠️ Bilinen Sorunlar ve Çözümleri

| Sorun | Neden Olur | Çözüm |
| ----- | ---------- | ----- |
| Kısayol çalışmıyor | Erişilebilirlik izni yok | Sistem Ayarları → Gizlilik ve Güvenlik → Erişilebilirlik → AltTab açık olsun; uygulamayı yeniden başlat |
| Küçük resimler görünmüyor | Ekran kaydı izni verilmemiş | Sistem Ayarları → Ekran ve Sistem Ses Kaydı → AltTab'i etkinleştir |
| `Cmd + Tab` çakışması | macOS yerleşik kısayolu | `Option + Tab` kullan veya Preferences → Controls'tan farklı bir kombinasyon seç |
| Sanal makine / uzak masaüstü pencereleri listeyi dolduruyor | Tüm pencereler varsayılan olarak listelenir | Preferences → **Blacklists** → ilgili uygulamayı istisna olarak ekle |
| Bazı uygulamalar listede yok | Uygulama pencere bilgisini paylaşmıyor | Bilinen sınırlama; ilgili uygulamayı öne getirip tekrar dene |

---

## 🔗 Faydalı Bağlantılar

- 🌐 [Resmi Web Sitesi](https://alt-tab.app/tr/)
- ✨ [Ücretsiz Özellikler](https://alt-tab.app/tr/features)
- 💾 [GitHub Sayfası](https://github.com/lwouis/alt-tab-macos)
- 📖 [GitHub Wiki](https://github.com/lwouis/alt-tab-macos/wiki)
- 📦 [Homebrew Cask](https://formulae.brew.sh/cask/alt-tab)

---

## 📝 Notlar

> AltTab tamamen ücretsiz ve açık kaynaklıdır ([GPL-3.0](https://github.com/lwouis/alt-tab-macos/blob/master/LICENCE.md)). Pro sürüm; arama, ek görünüm stilleri, otomatik boyutlandırma ve birden fazla bağımsız kısayol gibi ileri özellikler ekler — bu rehber yalnızca ücretsiz sürümü kapsar. Günlük pencere geçişi için ücretsiz sürüm çoğu kullanıcıya fazlasıyla yeterlidir.

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
