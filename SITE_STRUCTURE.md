# 📁 Site Yapısı ve Dosya Organizasyonu

Bu dokümantasyon, projenizin dosya yapısını ve her bir bileşenin ne işe yaradığını açıklar.

## 🗂️ Ana Dizin Yapısı

```
my-portfolio/
│
├── .github/                    # GitHub özel konfigürasyonları
│   └── workflows/
│       └── hugo.yml            # Otomatik deployment workflow
│
├── content/                    # Site içeriği (Markdown dosyaları)
│   ├── _index.md              # Ana sayfa içeriği
│   ├── about/                 # Hakkımda bölümü
│   │   └── _index.md
│   ├── portfolio/             # Projeler bölümü
│   │   └── _index.md
│   ├── posts/                 # Blog yazıları / Proje detayları
│   │   ├── Veilborn.md
│   │   ├── ornek-web-projesi.md
│   │   └── mobil-uygulama.md
│   └── social/                # İletişim/Sosyal medya bölümü
│       └── _index.md
│
├── static/                     # Statik dosyalar (direkt kopyalanır)
│   ├── images/                # Görseller
│   │   └── README.md
│   └── videos/                # Videolar
│       └── README.md
│
├── themes/                     # Hugo temaları
│   └── nomad-tech/            # Kullanılan tema
│
├── public/                     # Build edilmiş site (git'e eklenmez)
│
├── resources/                  # Hugo tarafından oluşturulan cache
│   └── _gen/
│
├── .gitignore                  # Git tarafından ignore edilecek dosyalar
├── hugo.toml                   # Ana konfigürasyon dosyası
├── README.md                   # Genel proje dokümantasyonu
├── QUICK_START.md             # Hızlı başlangıç rehberi
├── DEPLOYMENT.md              # Deploy rehberi
└── SITE_STRUCTURE.md          # Bu dosya

```

## 📝 Önemli Dosyalar

### 1. `hugo.toml` - Ana Konfigürasyon

Site ayarlarını içerir:
- **baseURL**: Site URL'i
- **title**: Site başlığı
- **params**: Özel parametreler (yazar, açıklama, vb.)
- **menu**: Menü yapısı
- **social**: Sosyal medya linkleri
- **portfolio**: Öne çıkan projeler

### 2. `.github/workflows/hugo.yml` - Deployment

GitHub Actions workflow dosyası. `main` branch'e her push yapıldığında:
1. Hugo'yu yükler
2. Siteyi build eder
3. GitHub Pages'e deploy eder

### 3. `.gitignore`

Git'e eklenmemesi gereken dosyaları belirtir:
- `/public/` - Build çıktısı
- `/resources/` - Hugo cache
- `node_modules/` - Eğer varsa
- IDE ayarları

## 📄 İçerik Dosyaları (content/)

### Markdown Front Matter

Her içerik dosyasının üstünde meta bilgiler vardır:

```markdown
+++
date = '2026-01-07T10:00:00+03:00'  # Tarih
draft = false                         # Taslak mı?
title = 'Başlık'                      # Sayfa başlığı
tags = ["Tag1", "Tag2"]              # Etiketler
categories = ["Kategori"]            # Kategoriler
+++
```

### Sayfa Tipleri

1. **`_index.md`**: Bölüm ana sayfası (list page)
   - `content/_index.md` → Ana sayfa
   - `content/about/_index.md` → Hakkımda
   - `content/portfolio/_index.md` → Projeler listesi

2. **Normal dosyalar**: Tekil sayfalar (single page)
   - `content/posts/proje-adi.md` → Tek proje sayfası

## 🎨 Tema Yapısı (themes/nomad-tech/)

```
nomad-tech/
├── layouts/           # HTML template dosyaları
│   ├── _default/     # Varsayılan layoutlar
│   ├── partials/     # Yeniden kullanılabilir parçalar
│   └── index.html    # Ana sayfa template
│
├── assets/           # İşlenecek dosyalar (SCSS, JS)
│   ├── scss/        # Stil dosyaları
│   └── js/          # JavaScript dosyaları
│
├── static/          # Statik dosyalar (kopyalanır)
│
├── i18n/            # Çoklu dil desteği
│
└── theme.toml       # Tema bilgileri
```

## 🖼️ Statik Dosyalar (static/)

Bu klasördeki dosyalar olduğu gibi kopyalanır:

```
static/
├── images/
│   ├── projects/
│   │   └── veilborn/
│   │       └── screenshot1.png
│   └── profile/
│       └── avatar.jpg
│
├── videos/
│   └── demo.mp4
│
├── docs/           # PDF, dökümanlar vb.
│   └── cv.pdf
│
└── CNAME           # Özel domain için (opsiyonel)
```

**Erişim:**
```markdown
![Görsel](/images/projects/veilborn/screenshot1.png)
[CV İndir](/docs/cv.pdf)
```

## 🔄 İçerik Ekleme İş Akışı

### Yeni Proje Eklemek

1. **Dosya oluştur:**
   ```bash
   hugo new posts/proje-adi.md
   ```

2. **İçeriği düzenle:**
   ```markdown
   +++
   title = 'Proje Başlığı'
   tags = ["React", "Node.js"]
   +++
   
   # Proje detayları...
   ```

3. **Görselleri ekle:**
   - Görselleri `static/images/proje-adi/` klasörüne koy
   - Markdown'da referans ver: `![](/images/proje-adi/screenshot.png)`

4. **Test et:**
   ```bash
   hugo server -D
   ```

5. **Yayınla:**
   ```bash
   git add .
   git commit -m "Yeni proje eklendi: Proje Adı"
   git push
   ```

### Hakkımda Sayfasını Güncellemek

1. `content/about/_index.md` dosyasını aç
2. İçeriği düzenle
3. Kaydet ve push yap

### Menüye Yeni Öğe Eklemek

`hugo.toml` dosyasında:

```toml
[[menu.main]]
  name = "Yeni Sayfa"
  url = "/yeni-sayfa"
  weight = 6    # Sıralama (küçük sayı = solda)
```

## 🏗️ Build Süreci

### Geliştirme

```bash
hugo server -D
# -D: Draft içerikleri de göster
# -F: Gelecek tarihli içerikleri göster
# --navigateToChanged: Değişen sayfaya otomatik git
```

### Production Build

```bash
hugo --minify
# --minify: HTML/CSS/JS'i sıkıştır
# --gc: Garbage collection (gereksiz dosyaları sil)
```

Build çıktısı `public/` klasörüne gider.

## 🔧 Özelleştirme Noktaları

### Renkler ve Stiller

`themes/nomad-tech/assets/scss/` altındaki SCSS dosyalarını düzenleyin.

### Layout Değişiklikleri

`themes/nomad-tech/layouts/` altındaki HTML template dosyalarını özelleştirin.

**Önemli:** Tema dosyalarını direkt değiştirmek yerine, kök dizinde `layouts/` klasörü oluşturup override edin:

```
my-portfolio/
├── layouts/          # Kendi override'larınız
│   ├── index.html   # Ana sayfa layoutu (temadakini override eder)
│   └── partials/
│       └── footer.html  # Footer override
```

## 📊 Site Boyutu Optimizasyonu

### Görsel Optimizasyonu

```bash
# ImageMagick ile toplu optimize
mogrify -resize 1920x1080\> -quality 85 static/images/**/*.jpg

# PNG için
mogrify -resize 1920x1080\> static/images/**/*.png
```

### Build Boyutu

`public/` klasörü boyutunu kontrol edin:

```bash
# Windows PowerShell
Get-ChildItem -Path public -Recurse | Measure-Object -Property Length -Sum

# Linux/Mac
du -sh public/
```

**İdeal:** < 10MB (medya dosyaları hariç)

## 🔍 SEO ve Meta Bilgiler

Her sayfa için meta bilgileri `hugo.toml` ve front matter'da tanımlayın:

```markdown
+++
title = "Sayfa Başlığı"
description = "Bu sayfa hakkında kısa açıklama (SEO için)"
+++
```

`hugo.toml`:
```toml
[params]
  description = "Site genel açıklaması"
  keywords = ["anahtar", "kelimeler"]
  
  [params.author]
    name = "Adınız"
```

## 📱 Responsive Test

Site otomatik olarak responsive, ama test etmek için:

1. `hugo server -D` çalıştırın
2. Tarayıcıda F12 açın
3. Device toolbar'ı aktifleştirin
4. Farklı cihaz boyutlarında test edin

## 🐛 Debug İpuçları

### Build Hataları

```bash
# Verbose output ile build
hugo -v

# Debug mode
hugo --debug
```

### Cache Sorunları

```bash
# Cache'i temizle
hugo --gc
rm -rf resources/_gen
rm -rf public
```

### Tema Bulunamıyor

```bash
# Tema submodule'ünü güncelle
git submodule update --init --recursive
```

## 📚 Faydalı Hugo Komutları

```bash
# Yeni içerik oluştur
hugo new posts/baslik.md
hugo new about/sayfa.md

# Sunucuyu başlat
hugo server               # Normal
hugo server -D            # Draft'larla
hugo server --disableFastRender  # Cache olmadan

# Build
hugo                      # Normal build
hugo --minify            # Minified
hugo --environment production  # Production mode

# İstatistikler
hugo list all            # Tüm içerikleri listele
hugo list drafts         # Taslakları listele

# Bilgi
hugo version             # Versiyon
hugo config              # Konfigürasyonu göster
hugo env                 # Environment bilgileri
```

## 🎯 En İyi Pratikler

1. **Düzenli Commit:** Sık sık commit yapın, anlamlı mesajlar yazın
2. **Görsel Optimizasyonu:** Her zaman optimize edilmiş görseller kullanın
3. **Draft Kullanımı:** Tamamlanmamış içerikler için `draft = true`
4. **Kategori/Tag:** İçerikleri düzgün kategorize edin
5. **Mobile-First:** Mobil görünümü öncelik verin
6. **Performance:** Gereksiz plugin/script yüklemekten kaçının
7. **Backup:** Düzenli git commit/push yapın

---

**Bu yapı ile profesyonel bir portföy sitesi hazırlayabilirsiniz! 🚀**

Sorularınız için: [GitHub Issues](https://github.com/ibrahimcetin/ibrahimcetin.github.io/issues)


