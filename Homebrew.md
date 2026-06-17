# 🛠️ Homebrew

> **Kısa Açıklama:** macOS için komut satırı paket yöneticisi; CLI araçları (formula) ve masaüstü uygulamaları (cask) tek komutla kurmanı sağlar.

Güncel · macOS (Apple Silicon / Intel) · BSD-2-Clause / Açık Kaynak · Paket Yönetimi

---

## Genel Bakış

Homebrew, macOS'ta yazılım kurmanın en pratik yoludur. Terminal üzerinden `brew install` ile geliştirici araçlarını, `brew install --cask` ile masaüstü uygulamalarını `.dmg` indirip sürüklemek yerine doğrudan kurabilirsin.

Terminal'e alışkın değilsen grafik arayüz için **[Applite](Applite.md)** kullan - Homebrew Cask uygulamalarını tek tıkla kurar, günceller ve kaldırır.

---

## Öne Çıkan Özellikler

- **Formula** - CLI araçları ve kütüphaneler (`git`, `node`, `python` vb.)
- **Cask** - Masaüstü uygulamaları (`.app`); bu repodaki rehberlerin çoğu cask kullanır
- **Tek komutla kurulum** - İndirme, kurulum ve PATH yapılandırması otomatik
- **Güncelleme yönetimi** - `brew upgrade` ile tüm paketleri güncelle
- **Temiz kaldırma** - `brew uninstall` ile paketi ve bağımlılıklarını kaldır
- **Açık kaynak** - [Homebrew/brew](https://github.com/Homebrew/brew) topluluk tarafından sürdürülür
- **Applite entegrasyonu** - Cask'leri grafik arayüzden yönetmek için [Applite](Applite.md) kullanılabilir

---

## Kurulum

### Adım 1: Homebrew'u kur

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

Kurulum sırasında Xcode Command Line Tools istenebilir - onayla.

### Adım 2: PATH ayarla

Kurulum bitince Terminal'de gösterilen **Next steps** komutlarını çalıştır.

**Apple Silicon (M serisi):**
```bash
echo 'eval "$(/opt/homebrew/bin/brew shellenv)"' >> ~/.zprofile
eval "$(/opt/homebrew/bin/brew shellenv)"
```

**Intel Mac:** Homebrew `/usr/local/bin/brew` konumuna kurulur; PATH genellikle otomatik ayarlanır.

### Adım 3: Kurulumu doğrula

```bash
brew --version
brew doctor
```

`brew doctor` uyarı vermezse kurulum tamamdır.

### Adım 4 (isteğe bağlı): Applite ile grafik arayüz

Cask uygulamalarını Terminal olmadan yönetmek için:

```bash
brew install --cask applite
```

Ayrıntılar: [Applite.md](Applite.md)

> Homebrew resmi sitesi: [brew.sh](https://brew.sh)

---

## İlk Kurulum Sonrası Öneriler

```bash
brew update    # Paket listesini yenile
brew doctor    # PATH ve izin sorunlarını kontrol et
brew cleanup   # Eski sürüm dosyalarını temizle (isteğe bağlı)
```

Applite kullanıyorsan ilk açılışta **Use existing brew** seçeneğini seç - böylece mevcut cask'lerin Applite'ta görünür.

---

## Temel Kullanım

### Formula (CLI aracı) kurma

```bash
brew install git
brew install node
brew list                  # Kurulu formulalar
brew uninstall git
```

### Cask (masaüstü uygulaması) kurma

```bash
brew install --cask vlc
brew install --cask brave-browser
brew list --cask           # Kurulu cask'ler
brew uninstall --cask vlc
```

### Güncelleme

```bash
brew update                # Paket listesini güncelle
brew upgrade               # Tüm formulaları güncelle
brew upgrade --cask        # Tüm cask'leri güncelle
brew upgrade --cask vlc    # Tek cask güncelle
```

### Bilgi ve arama

```bash
brew search firefox        # Paket ara
brew info --cask vlc       # Cask ayrıntıları
brew outdated --cask       # Güncellenebilir cask'ler
```

### Applite ile (grafik arayüz)

| İşlem | Terminal | Applite |
|---|---|---|
| Uygulama kur | `brew install --cask <uygulama>` | Discover → Install |
| Güncelle | `brew upgrade --cask <uygulama>` | Updates → Update |
| Kaldır | `brew uninstall --cask <uygulama>` | Installed → Uninstall |
| Ara | `brew search <uygulama>` | Arama çubuğu |

---

## Cask Envanteri

Mac'indeki uygulamaları Brew yönetimi açısından üç gruba ayıran script: Brew ile kurulmuş, Brew'de mevcut ama Brew dışı kurulmuş, ve Brew'de hiç bulunmayanlar.

### Script

Aşağıdaki bloğu doğrudan Terminal'e yapıştırabilirsin:

```bash
#!/usr/bin/env bash

echo "\n📦 Brew ile Yüklü Cask'ler:\n"
echo "━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━"
count0=0
for cask in $(brew list --cask); do
    count0=$((count0 + 1))
    printf "  %-3s %s\n" "$count0." "$cask"
done
echo "━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━"
echo "  Toplam: $count0 uygulama\n"

echo "\n🍺 Brew'de Mevcut Ama Brew ile Yüklü Olmayan Uygulamalar:\n"
echo "━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━"
count1=0
for app in /Applications/*.app; do
    app_name=$(basename "$app" .app | tr '[:upper:]' '[:lower:]' | tr ' ' '-')
    if brew info --cask "$app_name" &>/dev/null && ! brew list --cask "$app_name" &>/dev/null; then
        count1=$((count1 + 1))
        printf "  %-3s %-30s %s\n" "$count1." "$app_name" "→ brew install --cask --force $app_name"
    fi
done
echo "━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━"
echo "  Toplam: $count1 uygulama\n"

echo "\n⚠️  Yüklü Ama Brew'de Olmayan Uygulamalar:\n"
echo "━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━"
count2=0
for app in /Applications/*.app; do
    app_name=$(basename "$app" .app | tr '[:upper:]' '[:lower:]' | tr ' ' '-')
    if ! brew info --cask "$app_name" &>/dev/null; then
        count2=$((count2 + 1))
        printf "  %-3s %s\n" "$count2." "$app_name"
    fi
done
echo "━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━"
echo "  Toplam: $count2 uygulama\n"
```

Sık kullanacaksan dosyaya kaydet:

```bash
chmod +x brew-cask-envanter.sh
./brew-cask-envanter.sh

# Çıktıyı dosyaya yazmak için:
./brew-cask-envanter.sh > envanter.txt
```

### Örnek çıktı

```
📦 Brew ile Yüklü Cask'ler:
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
  1.  brave-browser
  2.  raycast
  3.  vlc
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
  Toplam: 3 uygulama

🍺 Brew'de Mevcut Ama Brew ile Yüklü Olmayan Uygulamalar:
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
  1.  firefox                        → brew install --cask --force firefox
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
  Toplam: 1 uygulama

⚠️  Yüklü Ama Brew'de Olmayan Uygulamalar:
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
  1.  xcode
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
  Toplam: 1 uygulama
```

### `--force` ile Brew kaydına alma

İkinci gruptaki uygulamalar sistende yüklü ama Brew'in haberi yok. Script'in önerdiği komutu çalıştırınca Brew o uygulamayı yönetmeye başlar:

```bash
brew install --cask --force firefox
```

Kurmadan önce `brew info --cask <isim>` ile doğru paketi hedeflediğini kontrol et.

---

## Bilinen Sorunlar ve Çözümleri

| Sorun | Neden Olur | Çözüm |
|---|---|---|
| `brew: command not found` | PATH ayarlanmamış | `eval "$(/opt/homebrew/bin/brew shellenv)"` çalıştır; `.zprofile`'a ekle |
| `brew doctor` uyarıları | Eski kurulum, izin sorunu | `brew doctor` çıktısındaki önerileri uygula |
| Cask kurulumu yavaş / başarısız | Ağ veya kaynak sorunu | `brew update` sonra tekrar dene; Applite'ta Mirror Downloads aç |
| Uygulama Applite'ta görünmüyor | Manuel kurulmuş (DMG, App Store) | `brew install --cask --force <uygulama>` ile Brew kaydına al |
| Formula ile cask karışıklığı | Yanlış komut | Masaüstü uygulamaları için `--cask` bayrağını kullan; CLI araçları için kullanma |

---

## Faydalı Bağlantılar

- 🌐 [Resmi Web Sitesi](https://brew.sh)
- 📖 [Homebrew Dokümantasyonu](https://docs.brew.sh)
- 💾 [GitHub - Homebrew/brew](https://github.com/Homebrew/brew)
- 📦 [Cask Kataloğu](https://formulae.brew.sh/cask/)
- 🧰 [Formula Kataloğu](https://formulae.brew.sh/formula/)
- 🖥️ [Applite - Grafik arayüz](Applite.md)

---

## Notlar

Homebrew bu repodaki tüm masaüstü uygulama rehberlerinin ortak altyapısıdır. Terminal rahatsa doğrudan `brew` komutlarını kullan; değilse kurulumdan hemen sonra [Applite](Applite.md) ile aynı cask ekosistemini grafik arayüzden yönet. Uygulama kalıntılarını temizlemek için [AppCleaner.md](AppCleaner.md) kullanılabilir.

---

*Son güncelleme: 2026-06-17*
