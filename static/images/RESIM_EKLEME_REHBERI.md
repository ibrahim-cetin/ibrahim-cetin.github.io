# 📸 Proje Resim Ekleme Rehberi

## Klasör Yapısı

```
static/images/
├── veilborn/
│   ├── cover.jpg          (Kapak görseli)
│   ├── screenshot1.jpg    (Ekran görüntüsü)
│   └── screenshot2.jpg
├── web-app/
│   └── cover.jpg
└── mobile-app/
    └── cover.jpg
```

## Resim Ekleme Adımları

### 1. Proje Klasörüne Resim Ekleyin

Resimlerinizi ilgili proje klasörüne koyun:
- Veilborn için: `static/images/veilborn/`
- Web App için: `static/images/web-app/`
- Mobile App için: `static/images/mobile-app/`

### 2. Markdown Dosyasında Kullanın

**Kapak Görseli** (Proje üstünde büyük görünür):
```markdown
+++
featured_image = "/images/veilborn/cover.jpg"
+++
```

**İçerikte Görsel:**
```markdown
![Açıklama](/images/veilborn/screenshot1.jpg)
```

### 3. Video Ekleme

**YouTube Video (Sayfa içinde oynatılır):**
```html
<div style="position: relative; padding-bottom: 56.25%; height: 0; overflow: hidden; margin: 2rem 0;">
  <iframe style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; border: 0; border-radius: 8px;" src="https://www.youtube.com/embed/VIDEO_ID" allowfullscreen></iframe>
</div>
```

**Yerel Video:**
```html
<video width="100%" controls style="border-radius: 8px; margin: 2rem 0;">
  <source src="/videos/demo.mp4" type="video/mp4">
</video>
```

## Önerilen Boyutlar

- **Kapak Görseli**: 1920x1080px (16:9)
- **Ekran Görüntüleri**: 1280x720px veya üstü
- **Dosya Boyutu**: < 2MB (optimize edilmiş)
- **Format**: JPG (fotoğraf), PNG (ekran görüntüsü)

## Optimizasyon İpuçları

1. Görselleri online araçlarla sıkıştırın: TinyPNG, Squoosh
2. Web için 85% kalite yeterlidir
3. Gereksiz metadata'yı temizleyin
4. Büyük videolar için YouTube kullanın

## Örnek Proje İçeriği

```markdown
+++
title = 'Veilborn'
featured_image = "/images/veilborn/cover.jpg"
+++

## Proje Hakkında
Açıklama...

## Ekran Görüntüleri
![Gameplay](/images/veilborn/screenshot1.jpg)

## Demo Video
<div style="position: relative; padding-bottom: 56.25%; height: 0;">
  <iframe src="https://www.youtube.com/embed/VIDEO_ID" ...></iframe>
</div>
```

---

**Not:** Görselleri ekledikten sonra Hugo sunucusunu yeniden başlatın veya hard refresh yapın.


