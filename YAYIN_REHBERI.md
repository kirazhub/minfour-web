# Minfour Web Yayın Rehberi

Bu klasördeki dosyaları **GitHub Pages** üzerinden ücretsiz olarak yayınlayacağız.
Sonuçta `https://kullaniciadin.github.io/minfour-web/` gibi gerçek bir adres elde edeceksin
ve bu adresi App Store Connect'e gizlilik politikası URL'i olarak verebileceksin.

---

## Klasör İçeriği

```
web-yayin/
├── index.html         ← Ana sayfa (logo, tagline, 3 link kartı)
├── privacy.html       ← Gizlilik Politikası (Türkçe)
├── privacy-en.html    ← Privacy Policy (English)
├── terms.html         ← Kullanım Koşulları (Türkçe)
├── terms-en.html      ← Terms of Service (English)
├── style.css          ← Tüm sayfaların ortak stil dosyası
├── .nojekyll          ← GitHub Pages için (boş, dokunma)
└── YAYIN_REHBERI.md   ← Bu dosya
```

> **Not:** HTML dosyalarının içinde `[VERİ_SORUMLUSU_UNVAN]`, `[SAĞLAYICI_ADRES]`,
> `[SON_GÜNCELLEME_TARİHİ]` gibi köşeli parantezli yer tutucular var. Yayın öncesi
> bunları gerçek bilgilerle değiştirmen gerekiyor (ya da bana söyle, ben yapayım).

---

## 1. Adım — GitHub Hesabı

GitHub hesabın yoksa: <https://github.com/signup> — ücretsiz aç.
Hesabın varsa, doğrudan 2. adıma geç.

---

## 2. Adım — Yeni Repo Açma

1. GitHub'da sağ üstte **+** simgesine bas → **New repository**.
2. Şu bilgileri gir:
   - **Repository name:** `minfour-web`
   - **Description:** `Minfour landing & legal pages`
   - **Public** seçili kalsın (GitHub Pages ücretsizi için gerekli).
   - "Add a README" işaretleme. (Boş olsun.)
3. **Create repository** tuşuna bas.

---

## 3. Adım — Dosyaları Yükleme (En Kolay Yol)

1. Açılan boş repo sayfasında **"uploading an existing file"** linkine tıkla.
2. `web-yayin/` klasörünün **içindeki tüm dosyaları** (klasörü değil, içindekileri) sürükle-bırak
   yap. Yüklenecek dosyalar:
   - `index.html`
   - `privacy.html`
   - `privacy-en.html`
   - `terms.html`
   - `terms-en.html`
   - `style.css`
   - `.nojekyll`
3. Aşağıda commit mesajına `İlk yayın` yaz, **Commit changes** tuşuna bas.

> **Not:** `.nojekyll` dosyası gizli bir dosya olduğu için Mac'te Finder'da görünmeyebilir.
> Görmek için Finder'da `Cmd + Shift + .` tuşlarına bas.

---

## 4. Adım — GitHub Pages'i Aktif Etme

1. Repo sayfasında üstteki **Settings** sekmesine tıkla.
2. Sol menüden **Pages** seç.
3. **Build and deployment** kısmında:
   - **Source:** "Deploy from a branch"
   - **Branch:** `main` seç, klasör `/ (root)` kalsın.
4. **Save** tuşuna bas.
5. 1–2 dakika bekle. Sayfa kendini yeniler ve şu mesaj çıkar:
   > "Your site is live at https://kullaniciadin.github.io/minfour-web/"

Bu URL'i tıkla — landing sayfan canlı olmalı.

---

## 5. Adım — URL'leri Test Et

Aşağıdaki URL'lerin hepsi çalışmalı:

```
https://kullaniciadin.github.io/minfour-web/
https://kullaniciadin.github.io/minfour-web/privacy.html
https://kullaniciadin.github.io/minfour-web/privacy-en.html
https://kullaniciadin.github.io/minfour-web/terms.html
https://kullaniciadin.github.io/minfour-web/terms-en.html
```

Her sayfada başlıklar, tablolar, dilim değiştirme linkleri çalışıyor mu kontrol et.

---

## 6. Adım — Custom Domain (Opsiyonel: minfour.app)

Eğer `minfour.app` alan adına sahipsen, GitHub Pages'i bu adrese bağlayabilirsin:

### A. GitHub tarafında
1. Repo → **Settings** → **Pages**.
2. **Custom domain** kutusuna `minfour.app` yaz, **Save**.
3. **Enforce HTTPS** kutusunu işaretle (DNS yayıldıktan sonra aktif olur, ~1 saat).

### B. Domain sağlayıcı tarafında (Namecheap, GoDaddy, vs.)
DNS ayarlarına şu kayıtları ekle:

**Apex domain (minfour.app) için A kayıtları:**
```
A    @    185.199.108.153
A    @    185.199.109.153
A    @    185.199.110.153
A    @    185.199.111.153
```

**www subdomain için CNAME kaydı:**
```
CNAME    www    kullaniciadin.github.io
```

DNS değişiklikleri 5 dakika ile birkaç saat arasında yayılır. Sabırla bekle.

> **Önemli:** Custom domain ayarlandığında repo'nun kökünde otomatik olarak `CNAME`
> isimli bir dosya oluşur. Bu dosyayı silme.

---

## 7. Adım — App Store Connect'e Privacy URL Ekleme

1. <https://appstoreconnect.apple.com> adresinden giriş yap.
2. **My Apps** → **Minfour** → sol menüden **App Information**.
3. Aşağı kaydır, **General Information** kısmında **Privacy Policy URL** alanını bul.
4. Şu URL'i gir:
   ```
   https://kullaniciadin.github.io/minfour-web/privacy.html
   ```
   (veya custom domain varsa: `https://minfour.app/privacy.html`)
5. **Save** tuşuna bas.

### App Privacy bölümü (zorunlu)
1. Sol menüden **App Privacy** sekmesi.
2. **Edit** → "Privacy Policy" alanına aynı URL'i ekle.
3. Veri toplama detaylarını ayrıca doldur (Gizlilik Politikası'ndaki bölümlerden faydalan).

### Terms of Service için (opsiyonel)
App Store her uygulama için zorunlu kılmaz, ancak abonelik içeren uygulamalarda
**Terms of Use (EULA)** alanına şu URL'i girmen iyi olur:
```
https://kullaniciadin.github.io/minfour-web/terms.html
```

---

## 8. Adım — Google Play Console (Android için)

Android'e de yayınlayacaksan:
1. <https://play.google.com/console>
2. **Minfour** → sol menü → **Policy** → **App content** → **Privacy Policy**.
3. Aynı URL'i yapıştır → **Save**.

---

## Güncelleme Yapmak İstersen

1. Yerelde dosyayı değiştir (ya da bana söyle).
2. GitHub repo sayfasında dosyaya tıkla → kalem ikonu → değişiklik yap → **Commit**.
3. 1–2 dakika içinde site otomatik güncellenir.

---

## Sorun Çıkarsa

- **Sayfa açılmıyor:** Settings → Pages bölümünde URL'in yanında "Your site is live" mesajını ara. Yoksa yayın daha tamamlanmamış demektir, 5 dk daha bekle.
- **CSS yüklenmiyor:** `style.css` dosyasını yüklemeyi unutmuş olabilirsin. Repo'ya gir, kontrol et.
- **Türkçe karakter bozuk:** Tüm HTML dosyalarında `<meta charset="UTF-8">` zaten var, sorun olmamalı. Olduysa bana söyle.
- **404 hatası:** Dosya isimleri **küçük harf** olmalı. `Privacy.html` değil `privacy.html` (GitHub Pages büyük/küçük harf duyarlıdır).

Herhangi bir sorunda bana yaz, anında çözeriz.
