# 🛠️ OnyX

> **Kısa Açıklama:** macOS sistem dosyalarını doğrulayan, bakım ve temizlik işlemlerini grafik arayüzden yöneten; Finder, Dock ve Safari ayarlarını düzenleyen ücretsiz çok işlevli sistem aracı.

v5.0.1 (Tahoe 26) · macOS sürümüne özel sürüm gerekir · Ücretsiz · Sistem / Bakım

---

## 📌 Genel Bakış

Terminal'de `diskutil verifyVolume`, önbellek silme veya LaunchServices veritabanını yeniden oluşturma gibi işlemler tek tek komut gerektirir. [Titanium Software](https://www.titanium-software.fr/) tarafından 2003'ten beri geliştirilen OnyX, bu tür bakım görevlerini sekmeli bir arayüzde toplar: sistem dosyası doğrulama, temizlik, bakım betikleri, uygulama kaldırma, Finder/Dock/Safari parametreleri ve veritabanı yeniden oluşturma. [AppCleaner](AppCleaner.md) uygulama kaldırmada daha odaklıdır; OnyX ise periyodik sistem bakımı ve macOS'un gizli ayarlarına erişim için kullanılır. **Her macOS ana sürümü için ayrı OnyX sürümü** gerekir — yanlış sürümü çalıştırmak sisteme zarar verebilir.

---

## ✨ Öne Çıkan Özellikler

- **Maintenance** — S.M.A.R.T. ve dosya sistemi doğrulama, Launch Services/Spotlight yeniden oluşturma, önbellek temizliği
- **Utilities** — Disk analizi, APFS anlık görüntüleri ve yerleşik macOS araçlarına kısayollar
- **Files** — Gizli dosya yönetimi, checksum ve kalıcı silme
- **Security** — SIP, FileVault, Güvenlik Duvarı, Gatekeeper ve XProtect durumu
- **Parameters** — Finder, Dock, Menus, Login, Safari ve diğer Apple uygulamalarının gizli ayarları
- **Otomasyon** — Seçili bakım ve temizlik görevlerini zamanla veya tek tıkla çalıştır
- **Sorunlu klasör/dosya silme** — Takılı kalan veya sorun çıkaran öğeleri güvenli şekilde temizle
- **Tamamen ücretsiz** — Bağış destekli; [Titanium Software](https://www.titanium-software.fr/en/donate.html) üzerinden geliştiriciye katkı yapılabilir

---

## 📥 İndirme ve Kurulum

### Yöntem 1: Homebrew (Önerilen)

Homebrew, macOS sürümüne uygun OnyX sürümünü kurar:

```bash
brew install --cask onyx
```

Güncelleme:

```bash
brew update
brew upgrade --cask onyx
```

> Homebrew yüklü değilse: [brew.sh](https://brew.sh) adresindeki komutu Terminal'de çalıştır.

### Yöntem 2: Resmi İndirme

1. [titanium-software.fr/en/onyx.html](https://www.titanium-software.fr/en/onyx.html) adresine git
2. **Mac'inin macOS ana sürümüne uygun** OnyX sürümünü indir — yanlış sürümü kullanma
3. `.zip` arşivini aç ve `OnyX.app` dosyasını **Applications** klasörüne taşı
4. Gatekeeper uyarısı çıkarsa: Sistem Ayarları → Gizlilik ve Güvenlik → Yine de Aç

> ⚠️ **Kritik:** Her macOS ana sürümü için ayrı OnyX vardır. Eski macOS için eski OnyX indirilebilir; Titanium Software artık eski sürümleri güncellemez.

**macOS uyumluluğu (özet):**

| macOS | OnyX sürümü | Not |
| ----- | ----------- | --- |
| Tahoe 26 | **5.0.1** | Güncel; Homebrew varsayılanı |
| Golden Gate 27 | 5.1.0 beta | Yalnızca Apple Silicon; beta |
| Sequoia 15 | 4.8.5 | Eski sürüm; güncelleme yok |
| Sonoma 14 | 4.6.2 | Eski sürüm |
| Ventura 13 | 4.4.7 | Eski sürüm |
| Monterey 12 | 4.2.7 | Eski sürüm |
| Big Sur 11 | 4.0.2 | Eski sürüm |
| Catalina 10.15 | 3.8.7 | Eski sürüm |

Tam liste: [Resmi OnyX sayfası — Old versions](https://www.titanium-software.fr/en/onyx.html)

---

## ⚙️ İlk Kurulum ve Önerilen Ayarlar

1. **Doğru sürümü doğrula:** OnyX'i açmadan önce macOS sürümünle eşleştiğinden emin ol (`sw_vers` veya  → Bu Mac Hakkında)
2. **Yönetici hesabı:** OnyX yalnızca yönetici hesabından açılır; işlemler için parola ister
3. **Tam Disk Erişimi (gerekirse):** Bazı bakım ve dosya işlemleri için Sistem Ayarları → Gizlilik ve Güvenlik → **Tam Disk Erişimi** → OnyX'i ekle
4. **Time Machine / yedek:** Agresif temizlik veya veritabanı yeniden oluşturma öncesi yedek al
5. **İlk çalıştırma — Maintenance:** **Maintenance** → **Verifying** bölümünden doğrulamayı çalıştır; sorun yoksa aşağıdaki periyodik bakım profilini uygula
6. **Periyodik bakım:** Ayda bir **Maintenance** → **Run Tasks** yeterli; günlük kullanımda agresif temizlik gerekmez

> 💡 OnyX bir "Mac hızlandırıcı" değildir. Önbellek silmek geçici alan açar; macOS önbellekleri zaten kendi yönetir. Amacı sorun giderme ve periyodik bakımdır.

### OnyX v5 sekme yapısı (Tahoe 26)

OnyX 5.x'te eski ayrı **Verify** ve **Cleaning** sekmeleri yoktur; işlevler **Maintenance** altında gruplanır. Üst araç çubuğundaki ana sekmeler:

| Sekme | Ne işe yarar |
| ----- | ------------ |
| **OnyX** | Karşılama ekranı, sürüm bilgisi |
| **Maintenance** | Doğrulama, veritabanı yeniden oluşturma, temizlik |
| **Utilities** | Disk analizi, yerleşik macOS araçlarına kısayollar |
| **Files** | Gizli dosya görünürlüğü, kalıcı silme, checksum |
| **Security** | SIP, FileVault, Güvenlik Duvarı, Gatekeeper durumu |
| **Find** | Sistemde dosya/klasör arama |
| **Parameters** | Finder, Dock, Safari ve diğer gizli macOS ayarları |
| **Info** | Donanım, disk ve sistem bilgisi |

**Parameters** alt sekmeleri: **General**, **Finder**, **Menus**, **Dock**, **Login**, **Applications**, **Misc.**

---

## 🚀 Temel Kullanım

### Maintenance (Bakım)

**Maintenance** sekmesi üç bölüme ayrılır: **Verifying**, **Rebuilding**, **Cleaning**. Görevleri seç → **Run Tasks** → yönetici parolasını gir.

**Önerilen periyodik bakım profili** (ayda bir, sorun yokken):

| Bölüm | Seçenek | Öneri | Ne zaman aç |
| ----- | ------- | ----- | ----------- |
| **Verifying** | S.M.A.R.T. status | ✅ Açık | Her periyodik bakımda |
| **Verifying** | Structure of the file system | ✅ Açık | Her periyodik bakımda |
| **Rebuilding** | Launch Services database | ✅ Açık | "Birlikte Aç" menüsü bozuksa veya ayda bir |
| **Rebuilding** | Spotlight index | ❌ Kapalı | Yalnızca arama bozuksa (saatler sürebilir) |
| **Rebuilding** | Mailboxes in Mail | ❌ Kapalı | Yalnızca Mail araması bozuksa |
| **Rebuilding** | Volume positions on the desktop | ❌ Kapalı | Masaüstü ikon konumları karıştıysa |
| **Cleaning** | System | ✅ Açık | Önbellek ve log temizliği |
| **Cleaning** | Applications | ✅ Açık | Uygulama önbellekleri |
| **Cleaning** | Internet | ⚠️ İsteğe bağlı | Tarayıcı geçmişi/oturumları silinir |
| **Cleaning** | Other | ⚠️ İsteğe bağlı | Ek geçici dosyalar; bilgi (ⓘ) simgesini oku |

> Temizlik kategorilerinin yanındaki **ⓘ** simgesine tıklayarak ne silineceğini oku. **Internet** ve **Other** işaretliyken oturum açık kalması gereken uygulamalar etkilenebilir.

### Security (Güvenlik)

**Security** sekmesi durumu gösterir; çoğu seçenek açık kalmalıdır:

| Seçenek | Öneri |
| ------- | ----- |
| System Integrity Protection (SIP) | ✅ Açık bırak (Recovery'den değiştirilir) |
| FileVault | ✅ Açık bırak |
| Firewall | ✅ Açık |
| Gatekeeper | ✅ Açık |
| Check for security responses | ✅ Açık |
| Automatically install Background Security Improvements | ✅ Açık |

Alt kısımdaki **Delete Junk Items** yalnızca güvenlik bileşenlerinin eski kalıntılarını temizler; periyodik bakımda güvenle kullanılabilir. **Reload** ile XProtect sürümlerini yenile.

### Parameters (Parametreler)

Sistem Ayarları'nda olmayan gizli macOS tercihlerini düzenler. Değişiklikler genelde oturumu kapat-aç veya ilgili uygulamayı yeniden başlatmayı gerektirir.

**General** — önerilen ayarlar:

| Ayar | Öneri |
| ---- | ----- |
| Screen capture file type | PNG |
| Show the date and the time in the names of captures | ✅ Açık |
| Display a shadow in window captures | ✅ Açık |
| Show the floating thumbnail | ✅ Açık |
| Show the mouse pointer | ❌ Kapalı (genelde) |
| Number of Recent Items | 10 |
| Animate alert messages | ✅ Açık |

**Finder** — çoğu kullanıcı için varsayılan yeterli; gizli dosyaları kalıcı göstermek istemiyorsan **Show hidden files and folders** kapalı kalsın.

**Dock** — **Don't display animation when showing or hiding the Dock** açıksa Dock animasyonu kapanır; tercihe bağlı. **Number of Recent Applications** → **None** önerilir (Dock kalabalıklaşmaz).

**Misc.** — önerilen ayarlar:

| Ayar | Öneri |
| ---- | ----- |
| Verify disk images | ✅ Açık |
| Mode of operation for CrashReporter | Basic |
| Use the accent menu | ✅ Açık |
| Show the Caps Lock indicator | ✅ Açık |
| Allow the startup volume to be indexed using Spotlight | ✅ Açık |

**Applications** alt sekmesindeki Safari Debug menüsü, Terminal odak özelliği vb. yalnızca geliştirici ihtiyacında açılmalı; günlük kullanımda kapalı bırak.

Her alt sekmede **Restore Defaults** ile o bölümü sıfırlayabilirsin.

### Utilities (Araçlar)

Disk dosya sistemi analizi, APFS anlık görüntü yönetimi, Wireless Diagnostics ve Directory Utility gibi yerleşik macOS araçlarına kısayol sağlar. Sorun giderme sırasında kullan.

### Files (Dosyalar)

Gizli dosya/klasör görünürlüğü, checksum hesaplama ve kalıcı silme (geri dönüşümsüz) içerir. Günlük kullanımda nadiren gerekir; silme işlemlerinde dikkatli ol.

### Find (Arama)

Sistem genelinde dosya ve klasör arar. Spotlight yeterli değilse veya belirli konumlarda arama gerekiyorsa kullan.

### Info (Bilgi)

Donanım, disk kapasitesi, bellek ve macOS sürümü gibi sistem bilgilerini gösterir; salt okunur.

### Uygulama kaldırma

OnyX 5.x'te uygulama kaldırma **Utilities** veya **Files** bölümlerinden erişilebilir (sürüme göre konum değişebilir). Günlük kaldırma için [AppCleaner](AppCleaner.md) daha pratiktir.

---

## ⚠️ Bilinen Sorunlar ve Çözümleri

| Sorun | Neden Olur | Çözüm |
| ----- | ---------- | ----- |
| OnyX açılmıyor / "wrong version" | macOS sürümüyle OnyX sürümü uyuşmuyor | [Resmi siteden](https://www.titanium-software.fr/en/onyx.html) doğru sürümü indir veya `brew upgrade --cask onyx` |
| Yönetici parolası kabul edilmiyor | Standart kullanıcı hesabı | Yönetici hesabıyla oturum aç |
| Temizlik sonrası uygulama ayarları sıfırlandı | Kullanıcı tercih/önbellek dosyaları silindi | Time Machine'den geri yükle; bir sonraki temizlikte o kategorileri işaretleme |
| Spotlight arama bozuldu | İndeks yeniden oluşturma devam ediyor | Birkaç saat bekle; sorun sürerse **Maintenance → Rebuilding → Spotlight index** ile yeniden oluştur |
| Safari/Finder garip davrandı | Parameters'da agresif değişiklik | OnyX → Parameters → **Restore defaults** veya ilgili uygulamayı sıfırla |
| Homebrew eski OnyX kurdu | macOS henüz cask'ta desteklenmiyor | Resmi siteden beta veya manuel sürüm indir |
| "Mac yavaşladı" beklentisi | Önbellek silme geçici etki yapar | OnyX'i yalnızca sorun giderme ve periyodik bakımda kullan; gereksiz agresif temizlikten kaçın |

---

## 🔗 Faydalı Bağlantılar

- 🌐 [Resmi Web Sitesi — OnyX](https://www.titanium-software.fr/en/onyx.html)
- 🏠 [Titanium Software](https://www.titanium-software.fr/)
- 💝 [Bağış](https://www.titanium-software.fr/en/donate.html)
- 📦 [Homebrew Cask](https://formulae.brew.sh/cask/onyx)
- 🧹 [AppCleaner (uygulama kaldırma)](AppCleaner.md)

---

## 📝 Notlar

> OnyX, macOS bakımında yıllardır güvenilen ücretsiz bir araçtır; CleanMyMac gibi ücretli alternatiflerin birçok temel işlevini karşılar. En kritik kural **doğru sürümü kullanmak**tır — Sequoia Mac'te Tahoe OnyX'i çalıştırma. Günlük uygulama kaldırma için [AppCleaner](AppCleaner.md) yeterli; OnyX'i ayda bir bakım, disk doğrulama veya Finder/Dock ince ayarı gerektiğinde açman yeterlidir. Titanium Software aynı geliştiricinin [Deeper](https://www.titanium-software.fr/en/deeper.html) aracını da sunar; OnyX ile örtüşen ama daha derin sistem ayarları içerir — ikisini aynı anda agresif kullanma.

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
