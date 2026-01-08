# İbrahim Çetin - Kişisel Portföy Sitesi

Bu repo, Hugo static site generator kullanılarak oluşturulmuş kişisel portföy web sitesidir.

## 🚀 Özellikler

- ✨ Modern ve temiz tasarım
- 📱 Responsive (mobil uyumlu)
- 🎨 Özelleştirilebilir tema (nomad-tech)
- 📝 Blog/Proje yazıları için Markdown desteği
- 🏷️ Tag ve kategori sistemi
- 🔍 SEO optimize
- ⚡ Hızlı yükleme
- 🌐 GitHub Pages entegrasyonu

## 📋 Gereksinimler

- [Hugo Extended](https://gohugo.io/installation/) (v0.120.0 veya üstü)
- Git

## 🛠️ Kurulum

### 1. Repository'yi klonlayın

```bash
git clone https://github.com/ibrahimcetin/ibrahimcetin.github.io.git
cd ibrahimcetin.github.io
```

### 2. Hugo'yu yükleyin

**Windows (Chocolatey):**
```bash
choco install hugo-extended
```

**macOS (Homebrew):**
```bash
brew install hugo
```

**Linux (Snap):**
```bash
snap install hugo
```

### 3. Temayı başlatın

Tema zaten `themes/nomad-tech` klasöründe mevcut. Eğer tema submodule olarak eklendiyse:

```bash
git submodule update --init --recursive
```

## 🚀 Yerel Geliştirme

### Siteyi yerel olarak çalıştırın

```bash
hugo server -D
```

Tarayıcınızda `http://localhost:1313` adresine gidin.

### Yeni içerik oluşturun

**Yeni blog yazısı:**
```bash
hugo new posts/yeni-proje.md
```

**Yeni sayfa:**
```bash
hugo new about/hakkimda.md
```

## 📝 İçerik Ekleme

### Proje Eklemek

1. `content/posts/` klasöründe yeni bir Markdown dosyası oluşturun
2. Front matter (üst bilgiler) ekleyin:

```markdown
+++
date = '2026-01-07T10:00:00+03:00'
draft = false
title = 'Proje Başlığı'
tags = ["React", "Node.js"]
categories = ["Web Geliştirme"]
+++

# Proje İçeriği
...
```

### Görsel Eklemek

1. Görselleri `static/images/` klasörüne koyun
2. Markdown içinde kullanın:

```markdown
![Açıklama](/images/screenshot.png)
```

### Video Eklemek

YouTube videoları için:

```markdown
{{< youtube VIDEO_ID >}}
```

Veya doğrudan video dosyası:

```markdown
<video width="100%" controls>
  <source src="/videos/demo.mp4" type="video/mp4">
</video>
```

## ⚙️ Konfigürasyon

`hugo.toml` dosyasını düzenleyerek siteyi özelleştirin:

```toml
baseURL = "https://ibrahimcetin.github.io/"
title = "İbrahim Çetin | Portfolyo"

[params]
  author = "İbrahim Çetin"
  subtitle = "Bilgisayar Mühendisi • Game Developer"
  
  [[params.social]]
    name = "GitHub"
    url = "https://github.com/ibrahimcetin"
```

## 🌐 GitHub Pages'e Deploy

### Otomatik Deployment (Önerilir)

Bu repo GitHub Actions ile otomatik deploy edilmek üzere yapılandırılmıştır.

1. GitHub repo ayarlarına gidin
2. **Settings > Pages** bölümüne gidin
3. **Source**: "GitHub Actions" seçin
4. `main` branch'e push yapın - otomatik deploy olur!

```bash
git add .
git commit -m "Site güncellemesi"
git push origin main
```

### Manuel Deployment

```bash
# Siteyi build edin
hugo --minify

# public klasörünü deploy edin
# (GitHub Pages için gh-pages branch'ine)
```

## 📂 Klasör Yapısı

```
my-portfolio/
├── .github/
│   └── workflows/
│       └── hugo.yml          # GitHub Actions workflow
├── content/
│   ├── _index.md             # Ana sayfa
│   ├── about/                # Hakkımda
│   ├── portfolio/            # Projeler
│   ├── posts/                # Blog yazıları
│   └── social/               # İletişim
├── static/
│   ├── images/               # Görseller
│   └── videos/               # Videolar
├── themes/
│   └── nomad-tech/           # Tema dosyaları
├── hugo.toml                 # Hugo konfigürasyonu
├── .gitignore
└── README.md
```

## 🎨 Özelleştirme

### Renkleri Değiştirme

`themes/nomad-tech/assets/scss/` klasöründeki SCSS dosyalarını düzenleyin.

### Menüyü Düzenleme

`hugo.toml` içinde `[menu]` bölümünü güncelleyin:

```toml
[[menu.main]]
  name = "Yeni Sayfa"
  url = "/yeni-sayfa"
  weight = 6
```

### Sosyal Medya Linklerini Güncelleme

`hugo.toml` içinde `[[params.social]]` bölümlerini güncelleyin.

## 📚 Faydalı Komutlar

```bash
# Siteyi build et (production)
hugo --minify

# Draft içerikleri de göster
hugo server -D

# Gelecek tarihli içerikleri göster
hugo server -F

# Yeni içerik oluştur
hugo new posts/yeni-yazi.md

# Build cache'i temizle
hugo --gc

# Hugo versiyonunu kontrol et
hugo version
```

## 🐛 Sorun Giderme

### Tema bulunamadı hatası

```bash
git submodule update --init --recursive
```

### CSS/JS dosyaları yüklenmiyor

`baseURL`'in doğru olduğundan emin olun ve siteyi yeniden build edin.

### GitHub Pages'de 404 hatası

- Repository adının `username.github.io` formatında olduğundan emin olun
- GitHub Pages ayarlarında source'un doğru seçildiğini kontrol edin

## 📄 Lisans

Bu proje MIT lisansı altında lisanslanmıştır.

## 🤝 Katkıda Bulunma

Önerileriniz için issue açabilir veya pull request gönderebilirsiniz.

## 📧 İletişim

- Website: [ibrahimcetin.github.io](https://ibrahimcetin.github.io)
- GitHub: [@ibrahimcetin](https://github.com/ibrahimcetin)
- LinkedIn: [ibrahim-cetin](https://linkedin.com/in/ibrahim-cetin)

---

⭐ Bu projeyi beğendiyseniz yıldız vermeyi unutmayın!

**Son Güncelleme:** Ocak 2026


