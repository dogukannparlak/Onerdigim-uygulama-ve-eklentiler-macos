# 🛠️ PeaZip

> **Kısa Açıklama:** 200'den fazla arşiv formatını açan, sıkıştıran ve şifreleyen; WinRAR/WinZip alternatifi ücretsiz, açık kaynaklı çapraz platform arşiv yöneticisi.

v11.1.0 · macOS 11+ (Apple Silicon / Intel) · LGPL-3.0 / açık kaynak · Arşiv / dosya yönetimi

---

## 📌 Genel Bakış

macOS'un yerleşik Archive Utility'si yalnızca temel `.zip` işlemlerini yapar; `.rar`, `.7z`, bölünmüş arşivler (`.001`, `.r01`) veya şifreli arşivler için yetmez. **PeaZip**, 7-Zip/p7zip, Brotli, Zstandard, FreeArc ve PAQ gibi açık kaynak motorları üzerine kurulu tam özellikli bir arşiv yöneticisidir - hem sıkıştırma/arşivleme hem dosya yönetimi (yer imi, yinelenen dosya arama, hash doğrulama) sunar.

Yalnızca hızlıca `.rar` veya `.zip` açmak istiyorsan [The Unarchiver](https://theunarchiver.com/) yeterli olabilir; GUI'den arşiv oluşturma, dönüştürme, güçlü şifreleme, iki faktörlü kimlik doğrulama (parola + keyfile) ve CLI betiği dışa aktarma istiyorsan PeaZip daha kapsamlıdır.

> ⚠️ macOS paketleri **kod imzalı değil**; ilk kurulumda quarantine bayrağını kaldırman gerekir (aşağıdaki adımlara bak).

---

## ✨ Öne Çıkan Özellikler

- **200+ format desteği** - 7Z, RAR, TAR, ZIP, ZIPX, ISO, ACE, CAB, DMG, GZ, BZ2, XZ, ZST, WIM ve daha fazlası
- **Arşiv oluşturma** - 7Z, ARC, Brotli, BZ2, GZ, PEA, TAR, WIM, Zstandard, ZIP, ZIPX
- **RAR açma** - Kutudan çıkar; isteğe bağlı Resmi UnRAR eklentisi (PLUGINS sayfası)
- **Güçlü şifreleme** - AES, Twofish, Serpent; isteğe bağlı iki faktörlü kimlik doğrulama (parola + keyfile)
- **GUI → CLI dışa aktarma** - Arşivleme/çıkarma ekranındaki **Console** sekmesinden görevi komut satırı betiği olarak kaydet
- **Dosya yöneticisi** - Yer imi, arşiv içi arama, yinelenen dosya tespiti, metin/hex/görüntü görüntüleyici
- **Hash ve checksum** - Geniş hash fonksiyonlarıyla dosya doğrulama
- **Taşınabilir kullanım** - Kurulum zorunlu değil; ağ yolundan veya harici sürücüden çalıştırılabilir
- **macOS bağlam menüsü** - DMG içindeki Automator `.workflow` betikleriyle sağ tık menüsüne ekleme
- **Çapraz platform** - Linux, macOS ve Windows'ta aynı arayüz; açık kaynak ([LGPL-3.0](https://github.com/peazip/PeaZip/blob/sources/LICENSE))

---

## 📥 İndirme ve Kurulum

### Yöntem 1: Resmi site / GitHub Releases (Önerilen)

Homebrew Cask'te henüz resmi bir `peazip` formülü yok.

1. [peazip.github.io](https://peazip.github.io/index.html) veya [GitHub Releases](https://github.com/peazip/PeaZip/releases/latest) sayfasına git
2. Mimarine uygun **macOS DMG** paketini indir:
   - **Apple Silicon (M1/M2/M3/M4…)** → `aarch64` / Darwin ARM build
   - **Intel Mac** → `x86_64` / Darwin Intel build
3. DMG'yi aç → `peazip.app` dosyasını **Applications** klasörüne sürükle
4. Terminal'de quarantine bayrağını kaldır:

```bash
xattr -dr com.apple.quarantine /Applications/peazip.app
```

5. PeaZip'i aç; ilk çalıştırmada erişim izni istenirse **OK** de

> ⚠️ Yalnızca [peazip.github.io](https://peazip.github.io/index.html), [github.com/peazip/PeaZip](https://github.com/peazip/PeaZip) veya [SourceForge](https://sourceforge.net/projects/peazip/) resmi kaynaklarından indir. Paket imzalı değil; indirdikten sonra [SHA256 hash](https://peazip.github.io/changelog.html) değerlerini doğrula.

**Gatekeeper uyarıları:**

| Mesaj | Çözüm |
| ----- | ----- |
| *"peazip.app is damaged and can't be opened"* | Yukarıdaki `xattr` komutunu çalıştır |
| *"developer cannot be verified"* | Sağ tık → **Open** veya Gizlilik ve Güvenlik → **Open Anyway** |

Eski macOS sürümlerinde sıkıştırılmış DMG açılmıyorsa Intel paketi **ZIP** olarak da sunulur; aynı kurulum adımları geçerlidir.

### Yöntem 2: Taşınabilir (Portable) kullanım

`peazip.app` dosyasını Applications dışında istediğin konuma taşıyabilirsin (harici disk, ağ yolu vb.). Yapılandırma `~/.config` altına kaydedilir. DMG'den doğrudan çalıştırıp oturum kapanınca silinmesini de tercih edebilirsin - kalıcı kullanım için Applications'a kopyalamak daha pratiktir.

### Yöntem 3: Kaynaktan derleme

PeaZip **Lazarus/FreePascal** ile derlenir. Ayrıntılı talimatlar: [peazip-sources.html](https://peazip.github.io/peazip-sources.html) ve [GitHub Wiki](https://github.com/peazip/PeaZip/wiki).

---

## ⚙️ İlk Kurulum ve Önerilen Ayarlar

1. **Quarantine kaldır:** Kurulumdan hemen sonra `xattr -dr com.apple.quarantine /Applications/peazip.app` komutunu çalıştır
2. **Hash doğrula:** [Changelog / SHA256](https://peazip.github.io/changelog.html) sayfasındaki değerlerle indirdiğin paketi karşılaştır
3. **Bağlam menüsü (isteğe bağlı):** DMG kökündeki **macOS service menus** klasöründeki `.workflow` dosyalarına çift tıkla - *Add to archive*, *Extract*, *Open with PeaZip* sağ tık menüsüne eklenir
4. **7z alternatif algoritmalar (isteğe bağlı):** Brotli, LZ4, Zstd gibi gelişmiş `.7z` sıkıştırma istiyorsan **Options → Settings → Advanced → 7z / p7zip alias** değerini `7zalt` yap - *vanilla* 7-Zip ile uyumluluk bozulabilir; paylaşım arşivlerinde LZMA2/BZip2 tercih et
5. **Tema:** Açık/koyu mod ve alternatif temalar **Options → Settings** veya [Themes](https://peazip.github.io/peazip-themes.html) sayfasından

> 💡 Bağlam menüsü betikleri `~/Library/Services/` altına kurulur. Kaldırmak için ilgili `.workflow` dosyasını sil veya Sistem Ayarları → Klavye → Kısayollar → Hizmetler'den devre dışı bırak.

---

## 🚀 Temel Kullanım

### Arşiv açma / çıkarma

1. `.rar`, `.7z`, `.zip` veya desteklenen herhangi bir arşive **çift tıkla** - PeaZip varsayılan uygulama olarak atanmışsa doğrudan açılır
2. Veya PeaZip'i aç → arşivi pencereye **sürükle-bırak** → **Extract** (Çıkar)
3. Hedef klasörü seç → onayla

**Sağ tık menüsü:** Service menu kuruluysa dosyaya sağ tık → **Extract with PeaZip** (veya benzeri).

### Arşiv oluşturma

1. PeaZip'i aç → sıkıştırmak istediğin dosya/klasörleri seç veya sürükle
2. **Add** (Ekle) → format seç (ZIP, 7Z, TAR, ZST vb.)
3. Sıkıştırma seviyesi ve parola ayarla
4. **OK** ile arşivi oluştur

### Şifreli arşiv

1. Arşiv oluşturma ekranında **Encryption** bölümünü aç
2. Parola gir; isteğe bağlı **keyfile** (anahtar dosyası) ekle - iki faktörlü kimlik doğrulama
3. Algoritma olarak AES, Twofish veya Serpent seçilebilir

### GUI görevini CLI betiğine dönüştürme

1. Arşivleme veya çıkarma ekranında görevi GUI'de tanımla
2. **Console** sekmesine geç
3. Oluşan komut satırını kopyala veya betik olarak kaydet - yedekleme otomasyonu veya Terminal'den tekrar kullanım için ideal

### Dosya bölme / birleştirme

**Tools** menüsünden büyük dosyaları parçalara ayır veya `.001` / `.r01` gibi bölünmüş arşivleri birleştir.

### Hash doğrulama

Dosya veya arşiv seç → **Tools → Checksum / hash** ile bütünlük kontrolü yap.

### Klavye ve arayüz

PeaZip tam bir dosya yöneticisi arayüzü kullanır; temel işlemler menü ve sürükle-bırak ile yapılır. Sık kullanılan eylemler için bağlam menüsü ve araç çubuğu kısayollarını tercihine göre özelleştir.

---

## ⚠️ Bilinen Sorunlar ve Çözümleri

| Sorun | Neden Olur | Çözüm |
| ----- | ---------- | ----- |
| *"App is damaged"* veya açılmıyor | Safari quarantine bayrağı | `xattr -dr com.apple.quarantine /Applications/peazip.app` |
| Geliştirici doğrulanamadı | Paket imzalı değil | Sağ tık → Open veya Gizlilik ve Güvenlik → Open Anyway |
| RAR **oluştur**ulamıyor | RAR lisans kısıtı | RAR yazma için sistemde WinRar kurulu olmalı; yalnızca açma kutudan çıkar |
| ACE açılmıyor | Tescilli UNACE eklentisi gerekir | [PLUGINS](https://peazip.github.io/peazip-add-ons.html) sayfasından WinACE UNACE eklentisini kur |
| 7zalt arşivleri başka uygulamada açılmıyor | Alternatif p7zip fork kullanıldı | Paylaşım arşivlerinde standart LZMA2/BZip2 kullan |
| Homebrew ile kurulamıyor | Resmi Cask henüz yok | Resmi siteden veya GitHub Releases'ten indir |
| Sahte PeaZip paketleri | Üçüncü taraf siteler | Yalnızca resmi kaynaklardan indir; SHA256 doğrula |

---

## 🔗 Faydalı Bağlantılar

- 🌐 [Resmi Web Sitesi](https://peazip.github.io/index.html)
- 🍎 [PeaZip for macOS](https://peazip.github.io/peazip-macos.html)
- 💾 [GitHub Sayfası](https://github.com/peazip/PeaZip)
- 📦 [GitHub Releases](https://github.com/peazip/PeaZip/releases/latest)
- 📖 [SSS / Yardım](https://peazip.github.io/peazip-help-faq.html)
- 🔌 [Eklentiler (PLUGINS)](https://peazip.github.io/peazip-add-ons.html)
- 📊 [Sıkıştırma benchmark](https://peazip.github.io/peazip-compression-benchmark.html)
- 🔐 [TOS ve Gizlilik](https://peazip.github.io/peazip-tos-privacy.html)
- 🗣️ [Reddit topluluğu](https://www.reddit.com/r/PeaZip/)

---

## 📝 Notlar

> PeaZip, macOS'ta ücretsiz ve açık kaynaklı en kapsamlı arşiv yöneticilerinden biridir. RAR açma, 7Z/Zstandard sıkıştırma, şifreleme ve CLI dışa aktarma gibi gelişmiş ihtiyaçları tek uygulamada toplar. Yerleşik Archive Utility veya The Unarchiver yalnızca açma odaklıdır; arşiv oluşturma, dönüştürme ve otomasyon istiyorsan PeaZip belirgin avantaj sağlar. Paketler imzalı olmadığı için kurulumda `xattr` adımını atlama; indirme bütünlüğünü resmi SHA256 hash listesiyle doğrula.

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
