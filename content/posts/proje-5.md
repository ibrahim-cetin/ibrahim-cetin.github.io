+++
date = '2026-01-03T10:00:00+03:00'
draft = false
title = 'VR Room Configurator'
tags = ["Unity", "VR", "Grid System"]
categories = ["Oyun Geliştirme"]
featured_image = "/images/proje-5/cover.jpg"
+++

Bu proje; kullanıcılara sanal gerçeklik ortamında, tamamen **modüler ve özelleştirilebilir yaşam alanları** tasarlama imkanı sunan bir iç mimari ve dekorasyon simülasyonudur. Kullanıcılar, sıfırdan bir oda inşa edip içini diledikleri gibi döşeyebilir ve materyal seçimleriyle tasarımı kişiselleştirebilirler.

## Proje Özeti

Proje, karmaşık yerleştirme algoritmalarını VR'ın daldırıcı dünyasıyla birleştirir. Bir mobilya mağazası veya iç mimari çözüm aracı gibi çalışan sistem, kullanıcının kısıtlı bir alanda (Grid) profesyonel tasarımlar yapmasını sağlar.

## Teknik Öne Çıkanlar

### 1. Dinamik Grid (Izgara) Yerleşim Sistemi

Oda oluşturma süreci, 10x10 gibi ölçeklenebilir bir grid tabanı üzerine kurulmuştur.

**Hassas Yerleşim:** Nesnelerin grid hücrelerine tam oturmasını sağlayan "Snap" sistemi sayesinde, VR kontrolcüleriyle yapılan yerleştirmelerde milimetrik hassasiyet elde edilir.

**Prosedürel Oda Oluşturma:** Kullanıcı, seçtiği oda tipine göre duvar ve zemin yapısını dinamik olarak değiştirebilir.

### 2. Runtime Nesne ve Materyal Özelleştirme

Oyun içerisinde statik modeller yerine, tamamen dinamik bir yapı kurgulanmıştır:

**Panel Tabanlı Etkileşim:** VR ortamına entegre edilmiş spatial (uzamsal) UI panelleri üzerinden eşya kütüphanesine erişim sağlanır.

**Anlık Materyal Değişimi:** Seçilen mobilyaların kumaş, ahşap veya metal gibi materyalleri Runtime (çalışma zamanı) sırasında değiştirilebilir. Bu sistem, Shader ve Material Property blokları kullanılarak performans dostu bir şekilde optimize edilmiştir.

### 3. VR UX ve Spatial UI

**Kullanıcı Dostu Arayüz:** VR'da derinlik algısını bozmayan, kullanıcıyı yormayan ergonomik menü tasarımları.

**Sezgisel Kontroller:** Eşyaları tutma, döndürme ve yerleştirme işlemleri VR kontrolcüleri için optimize edilmiş doğal etkileşimlerle (Grabbing & Raycasting) sağlanmıştır.

## Kullanım Alanları

- **E-Ticaret:** Mobilya markaları için sanal mağaza deneyimi
- **Gayrimenkul:** Henüz inşa edilmemiş projeler için interaktif kat planı sunumu
- **Eğitim:** İç mimarlık öğrencileri için ölçekli tasarım pratikleri

## Kaynak Kodları ve Geliştirme Süreci

Projenin tüm teknik altyapısına, modüler kod yapısına ve implementasyon detaylarına GitHub üzerinden ulaşabilirsiniz.

**Proje GitHub Reposu:** [github.com/ibrahim-cetin/VR_Room_Design](https://github.com/ibrahim-cetin/VR_Room_Design)

---

*Son güncelleme: Ocak 2026*


