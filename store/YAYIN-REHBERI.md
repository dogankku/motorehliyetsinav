# Play Store yayın rehberi

Uygulama bir web uygulamasıdır (PWA). Play Store'a, web uygulamasını saran bir Android paketi (Trusted Web Activity) olarak çıkar. Paketi PWABuilder adlı ücretsiz araç üretir; Android Studio gerekmez.

## 1. Siteyi yayına al (bir kez)

1. GitHub'da repo → **Settings → Pages** → Source: *Deploy from a branch* → Branch: `main`, klasör: `/ (root)` → **Save**.
2. Birkaç dakika sonra şu adres açılmalı: `https://dogankku.github.io/motorehliyetsinav/`
3. Gizlilik sayfası: `https://dogankku.github.io/motorehliyetsinav/gizlilik.html` — içindeki **[e-posta adresini buraya yaz]** yerini doldur.

Kendi alan adını alırsan (örn. `motorsinavi.com`), Pages ayarlarındaki *Custom domain* alanına yaz ve aşağıdaki adımlarda adres olarak onu kullan.

## 2. Android paketini üret (PWABuilder)

1. https://www.pwabuilder.com adresine git, site adresini yaz, **Start** de.
2. Rapor ekranında **Package For Stores → Android → Generate Package**.
3. Ayarlar:
   - **Package ID:** `io.github.dogankku.motorsinavi` (sonradan değiştirilemez; kendi alan adın olursa `com.alanadin.motorsinavi` gibi seçebilirsin)
   - **App name:** Motosiklet Ehliyet Sınavı 3D · **Short name:** Motor Sınavı
   - **Version:** 1.0.0 · **Version code:** 1
   - **Display mode:** Fullscreen · **Orientation:** Landscape
   - **Signing key:** *Create new*
4. **Download** ile zip'i indir. İçinden çıkanlar:
   - `*.aab` → Play Console'a yüklenecek dosya
   - `signing.keystore` ve `signing-key-info.txt` → **imza anahtarı. Kaybetme, kimseyle paylaşma, GitHub'a yükleme.** Güncellemeleri yayınlamak için gerekir.
   - `assetlinks.json` → 4. adımda kullanılacak

## 3. Play Console

1. https://play.google.com/console adresinde geliştirici hesabı aç: tek seferlik 25 ABD doları ücret ve kimlik doğrulaması gerekir.
2. **Uygulama oluştur:** Ad, varsayılan dil Türkçe, *Uygulama*, *Ücretsiz*.
3. **Ana mağaza girişi:** `LISTING.md` içindeki ad, kısa ve tam açıklama; bu klasördeki simge, öne çıkan görsel ve ekran görüntüleri.
4. **Uygulama içeriği:** `LISTING.md`'deki form yanıtları (gizlilik, reklam yok, içerik derecelendirmesi, hedef kitle, veri güvenliği).
5. **Test → Kapalı test:** Yeni sürüm oluştur, `.aab` dosyasını yükle, test kullanıcılarını e-posta listesiyle ekle.

### Yeni kişisel hesaplar için zorunlu test

13 Kasım 2023'ten sonra açılan kişisel hesaplarda uygulama doğrudan yayına çıkamaz: en az **12 test kullanıcısının 14 gün boyunca kesintisiz** kapalı teste katılmış olması gerekir. Sonra Play Console'dan "üretim erişimi" başvurusu yapılır. Arkadaş ve aileden 15–20 kişi eklemek, aradan çıkanlar için pay bırakır. Şirket (kuruluş) hesaplarında bu şart yoktur.

## 4. Adres çubuğunu gizlemek (Digital Asset Links)

Uygulamanın tarayıcı adres çubuğu olmadan tam ekran açılması için sitenin kök adresinde bir doğrulama dosyası olmalı:

```
https://<alan-adı>/.well-known/assetlinks.json
```

- İçine iki parmak izi girer: PWABuilder zip'indeki `assetlinks.json`'da olan ve Play Console → **Uygulama bütünlüğü → Uygulama imzalama** sayfasındaki *SHA-256 sertifika parmak izi*. Bu repodaki `.well-known/assetlinks.json` dosyası bir şablondur.
- **Önemli:** GitHub Pages'te proje sitesi (`dogankku.github.io/motorehliyetsinav/`) alt klasörde durduğu için dosyanın kök adreste olması gerekir. İki yol var:
  1. Kendi alan adını bağla; dosya bu repodan kök adreste yayınlanır (en kolayı).
  2. `dogankku.github.io` adında ayrı bir repo aç ve dosyayı onun `.well-known/` klasörüne koy.
- Bu dosya olmasa da uygulama çalışır; sadece üstte ince bir adres çubuğu görünür.

## 5. Güncelleme yayınlamak

- Oyunda yapılan değişiklikler siteye yüklendiği anda uygulamada da görünür; çoğu güncelleme için yeni paket gerekmez.
- Çevrimdışı önbelleğin yenilenmesi için `sw.js` içindeki `CACHE` adını artır (`motor-sinavi-v2` gibi).
- Simge, ad veya Android ayarları değişirse PWABuilder'da **aynı imza anahtarıyla** yeni paket üret ve *Version code*'u bir artır.
