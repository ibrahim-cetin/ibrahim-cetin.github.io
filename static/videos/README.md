# Videos Klasörü

Bu klasöre proje videolarınızı ve demo kayıtlarınızı ekleyin.

## Kullanım

Markdown dosyalarınızda şu şekilde kullanabilirsiniz:

```markdown
<video width="100%" controls>
  <source src="/videos/demo.mp4" type="video/mp4">
  Tarayıcınız video etiketini desteklemiyor.
</video>
```

## YouTube Videoları

Eğer videolarınız YouTube'daysa, daha kolay bir yöntem:

```markdown
{{< youtube VIDEO_ID >}}
```

## Öneriler

- Video dosyaları büyük olabileceğinden YouTube/Vimeo kullanımı önerilir
- Eğer yerel video kullanacaksanız:
  - MP4 formatı tercih edin
  - 1080p veya daha düşük çözünürlük kullanın
  - Dosya boyutunu 50MB altında tutmaya çalışın
  - Video editör ile sıkıştırma yapın

## Alternatif: Video Hosting Servisleri

- YouTube
- Vimeo
- Streamable
- Google Drive (embed ile)

Bu servisler bandwidth tasarrufu sağlar ve otomatik video optimizasyonu yapar.


