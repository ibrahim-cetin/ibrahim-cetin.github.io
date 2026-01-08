# 🚀 Hızlı Başlangıç Rehberi

Bu rehber, sitenizi hızlıca çalıştırmanız için gerekli adımları içerir.

## 1️⃣ Hugo'yu Yükleyin

### Windows
```powershell
# Chocolatey ile
choco install hugo-extended

# Veya Scoop ile
scoop install hugo-extended
```

### macOS
```bash
brew install hugo
```

### Linux
```bash
snap install hugo
```

## 2️⃣ Siteyi Çalıştırın

```bash
# Proje klasörüne gidin
cd my-portfolio

# Geliştirme sunucusunu başlatın
hugo server -D
```

Tarayıcınızda açın: http://localhost:1313

## 3️⃣ İçeriği Özelleştirin

### Kişisel Bilgilerinizi Güncelleyin

`hugo.toml` dosyasını açın ve aşağıdaki bilgileri güncelleyin:

```toml
[params]
  author = "Adınız"
  subtitle = "Başlık"
  description = "Açıklama"
```

### Sosyal Medya Linklerinizi Ekleyin

```toml
[[params.social]]
  name = "GitHub"
  url = "https://github.com/KULLANICI_ADINIZ"

[[params.social]]
  name = "LinkedIn"
  url = "https://linkedin.com/in/KULLANICI_ADINIZ"
```

### Hakkımda Sayfasını Güncelleyin

`content/about/_index.md` dosyasını düzenleyin.

## 4️⃣ Yeni Proje Ekleyin

```bash
# Yeni proje yazısı oluşturun
hugo new posts/proje-adi.md
```

Oluşan dosyayı düzenleyin:

```markdown
+++
date = '2026-01-07T10:00:00+03:00'
draft = false
title = 'Proje Başlığı'
tags = ["Tag1", "Tag2"]
categories = ["Kategori"]
+++

# Proje İçeriği

Buraya projenizin detaylarını yazın...
```

## 5️⃣ Görsel ve Video Ekleyin

### Görsel Ekleme
1. Görseli `static/images/` klasörüne koyun
2. Markdown'da kullanın:

```markdown
![Açıklama](/images/gorsel.png)
```

### Video Ekleme (YouTube)
```markdown
{{< youtube VIDEO_ID >}}
```

### Video Ekleme (Yerel)
1. Videoyu `static/videos/` klasörüne koyun
2. Markdown'da kullanın:

```markdown
<video width="100%" controls>
  <source src="/videos/demo.mp4" type="video/mp4">
</video>
```

## 6️⃣ GitHub'a Yükleyin

```bash
# İlk defa yüklüyorsanız
git init
git add .
git commit -m "İlk commit"
git branch -M main
git remote add origin https://github.com/KULLANICI_ADINIZ/KULLANICI_ADINIZ.github.io.git
git push -u origin main
```

```bash
# Güncelleme yaparken
git add .
git commit -m "Site güncellendi"
git push
```

## 7️⃣ GitHub Pages'i Aktifleştirin

1. GitHub repo sayfanıza gidin
2. **Settings** > **Pages** tıklayın
3. **Source** kısmında **GitHub Actions** seçin
4. Birkaç dakika bekleyin
5. Siteniz `https://KULLANICI_ADINIZ.github.io` adresinde yayında! 🎉

## ✅ Kontrol Listesi

- [ ] Hugo kurulumu yapıldı
- [ ] Site yerel olarak çalışıyor
- [ ] Kişisel bilgiler güncellendi (`hugo.toml`)
- [ ] Hakkımda sayfası dolduruldu
- [ ] En az bir proje eklendi
- [ ] Görseller yüklendi
- [ ] GitHub repository oluşturuldu
- [ ] GitHub Pages aktifleştirildi
- [ ] Site online!

## 🆘 Yardım

Sorun mu yaşıyorsunuz? `README.md` dosyasındaki "Sorun Giderme" bölümüne bakın.

## 📝 Sonraki Adımlar

- ✏️ Daha fazla proje ekleyin
- 🎨 Temayı özelleştirin
- 📊 Google Analytics ekleyin (opsiyonel)
- 🔍 SEO optimizasyonu yapın
- 📱 Sosyal medya kartları ekleyin

---

**Kolay gelsin! 🚀**


