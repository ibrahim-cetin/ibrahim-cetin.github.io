# 🌐 GitHub Pages Deployment Rehberi

Bu rehber, Hugo sitenizi GitHub Pages'e deploy etme adımlarını detaylı şekilde açıklar.

## Ön Hazırlık

### 1. GitHub Repository Oluşturun

Repository adı **mutlaka** şu formatta olmalıdır:
```
KULLANICI_ADINIZ.github.io
```

Örnek: `ibrahimcetin.github.io`

### 2. Repository Ayarları

- Repository **public** olmalıdır
- `main` branch'i kullanın

## Deployment Yöntemleri

Bu projede **GitHub Actions** kullanılarak otomatik deployment yapılandırılmıştır.

### Otomatik Deployment (Önerilen)

#### Adım 1: GitHub Actions'ı Aktifleştirin

1. GitHub repository sayfanıza gidin
2. **Settings** sekmesine tıklayın
3. Sol menüden **Pages** seçin
4. **Source** bölümünde **GitHub Actions** seçin

![GitHub Pages Settings](https://docs.github.com/assets/cb-47267/images/help/pages/publishing-source-drop-down.png)

#### Adım 2: Kodu Push Edin

```bash
# İlk commit
git add .
git commit -m "Initial commit"
git push origin main
```

#### Adım 3: Workflow'un Çalıştığını Kontrol Edin

1. Repository sayfasında **Actions** sekmesine gidin
2. "Deploy Hugo site to Pages" workflow'unun çalıştığını görmelisiniz
3. Yeşil tik işareti gördüğünüzde deployment tamamlanmıştır ✅

#### Adım 4: Sitenizi Ziyaret Edin

Birkaç dakika sonra siteniz şu adreste yayında olacak:
```
https://KULLANICI_ADINIZ.github.io
```

## Workflow Detayları

`.github/workflows/hugo.yml` dosyası otomatik deployment'ı yönetir:

- **Tetikleyici**: `main` branch'e her push
- **Hugo Versiyon**: 0.128.0 (Extended)
- **Build**: Production mode, minified
- **Deploy**: GitHub Pages'e otomatik

## Güncelleme Yapmak

Herhangi bir değişiklik yaptığınızda:

```bash
git add .
git commit -m "Güncelleme mesajı"
git push origin main
```

GitHub Actions otomatik olarak:
1. ✅ Kodu çeker
2. ✅ Hugo'yu yükler
3. ✅ Siteyi build eder
4. ✅ GitHub Pages'e deploy eder

Tüm süreç ~2-3 dakika sürer.

## Özel Domain Kullanımı (Opsiyonel)

Kendi domain'inizi kullanmak isterseniz:

### 1. CNAME Dosyası Oluşturun

`static/CNAME` dosyası oluşturun (uzantısız):

```
www.example.com
```

### 2. DNS Ayarlarını Yapılandırın

Domain sağlayıcınızın DNS ayarlarına gidin ve ekleyin:

**A Records:**
```
185.199.108.153
185.199.109.153
185.199.110.153
185.199.111.153
```

**CNAME Record:**
```
www -> KULLANICI_ADINIZ.github.io
```

### 3. GitHub Settings'te Domain'i Ekleyin

1. **Settings** > **Pages**
2. **Custom domain** alanına domain'inizi girin
3. **Save** tıklayın
4. **Enforce HTTPS** seçeneğini aktifleştirin

DNS propagation 24-48 saat sürebilir.

## Sorun Giderme

### Sayfa 404 Hatası Veriyor

**Sebep 1:** Repository adı yanlış
- ✅ Doğru: `kullaniciadi.github.io`
- ❌ Yanlış: `my-portfolio`, `website`, vb.

**Sebep 2:** GitHub Pages kaynağı yanlış seçilmiş
- Settings > Pages > Source: **GitHub Actions** olmalı

**Sebep 3:** Workflow başarısız
- Actions sekmesinden hataları kontrol edin

### CSS/JS Dosyaları Yüklenmiyor

`hugo.toml` dosyasında `baseURL` kontrol edin:

```toml
baseURL = "https://KULLANICI_ADINIZ.github.io/"
```

Sonunda `/` olmalı!

### Workflow Başarısız Oluyor

**Hata: "Permission denied"**

1. Settings > Actions > General
2. **Workflow permissions** bölümüne gidin
3. **Read and write permissions** seçin
4. Kaydedin ve tekrar push yapın

**Hata: "Hugo version not found"**

`.github/workflows/hugo.yml` dosyasındaki Hugo versiyonunu kontrol edin.

### Site Güncellenmiyor

1. Hard refresh yapın: `Ctrl + Shift + R` (Windows) veya `Cmd + Shift + R` (Mac)
2. GitHub Actions'da workflow'un başarılı olduğunu kontrol edin
3. Tarayıcı cache'ini temizleyin

## Build Önizlemesi (Yerel)

Deploy etmeden önce production build'i test edin:

```bash
# Build edin
hugo --minify

# Builded siteyi servis edin
cd public
python -m http.server 8000
```

Tarayıcıda: http://localhost:8000

## Performans İpuçları

### 1. Görselleri Optimize Edin

```bash
# ImageMagick kullanarak
mogrify -resize 1920x1080\> -quality 85 *.jpg
```

### 2. Minification Aktif

`hugo.toml` dosyasında:

```toml
[minify]
  disableCSS = false
  disableHTML = false
  disableJS = false
  disableJSON = false
```

### 3. Caching Stratejisi

GitHub Pages otomatik caching yapar. Ek bir şey yapmanıza gerek yok.

## Güvenlik

### HTTPS

GitHub Pages otomatik HTTPS sağlar. Özel domain kullanıyorsanız:

1. Settings > Pages
2. **Enforce HTTPS** ✅

### Şube Koruma

`main` branch'i korumak için:

1. Settings > Branches
2. **Add rule**
3. Branch name pattern: `main`
4. **Require a pull request before merging** ✅

## İzleme ve Analitik

### Google Analytics Ekleme

`hugo.toml` dosyasına:

```toml
[params]
  googleAnalytics = "G-XXXXXXXXXX"
```

### GitHub Actions Badge

README'ye ekleyin:

```markdown
![Deploy Status](https://github.com/KULLANICI_ADINIZ/KULLANICI_ADINIZ.github.io/workflows/Deploy%20Hugo%20site%20to%20Pages/badge.svg)
```

## Yardımcı Linkler

- [GitHub Pages Dokümantasyonu](https://docs.github.com/en/pages)
- [Hugo Deployment Guide](https://gohugo.io/hosting-and-deployment/hosting-on-github/)
- [GitHub Actions Dokümantasyonu](https://docs.github.com/en/actions)

## Deployment Checklist

- [ ] Repository adı doğru (`kullaniciadi.github.io`)
- [ ] Repository public
- [ ] `hugo.toml` içinde `baseURL` doğru
- [ ] `.github/workflows/hugo.yml` mevcut
- [ ] GitHub Pages source: GitHub Actions
- [ ] Workflow permissions: Read and write
- [ ] İlk push yapıldı
- [ ] Actions sekmesinde workflow başarılı (yeşil tik)
- [ ] Site açılıyor ve CSS yükleniyor
- [ ] Tüm sayfalar çalışıyor

---

🎉 **Tebrikler! Siteniz artık online!**

Sorularınız için GitHub Issues kullanabilirsiniz.


