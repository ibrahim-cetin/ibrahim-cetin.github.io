+++
date = '2026-01-06T10:00:00+03:00'
draft = false
title = 'Panik Yok'
tags = ["Unreal Engine", "MetaHuman", "IK System"]
categories = ["Oyun Geliştirme"]
featured_image = "/images/proje-2/cover.jpg"
+++

**Panik Yok**, çocuklara ve gençlere afet anlarında ne yapmaları gerektiğini sadece teorik olarak anlatmak yerine, onları bir karar mekanizmasının içine dahil eden interaktif bir eğitim oyunudur. **"Öğretmiyoruz, deneyimletiyoruz"** mottosuyla yola çıkan bu proje, afet bilincini ezberden çıkarıp bir refleks haline getirmeyi amaçlıyor.

## Proje Vizyonu

Geleneksel eğitim yöntemlerinin aksine **Panik Yok**, oyuncuyu korku ve stresle değil, merak ve bilinçle yönlendirir. Oyunda yanlış kararlar bir "Game Over" ekranıyla sonuçlanmaz; aksine o kararın neden yanlış olduğunu ve gerçek hayattaki karşılığını öğretir.

## Senaryo ve Oynanış

Bu versiyonumuzda, bir okulda meydana gelen deprem anını ve sonrasındaki tahliye sürecini simüle ettik. Oyuncu, **Gönüllü İtfaiyeci Mert** karakteriyle dinamik seçimler yaparak öğrencileri güvenli tahliye rotalarına yönlendirir.

## Teknik Katkılarım ve Geliştirme Süreci

Projenin geliştirilme aşamasında Unreal Engine ekosistemini kullanarak özellikle oyun mekanikleri ve karakter-çevre etkileşimi üzerine yoğunlaştım:

**Etkileşimli Obje Sistemi**  
Oyuncunun çevredeki kapılar, yangın tüpleri ve tahliye ekipmanlarıyla gerçek zamanlı etkileşime girmesini sağlayan esnek ve modüler bir etkileşim sistemi (Interaction System) kurguladım.

**IK (Inverse Kinematics) Karakter Animasyonları**  
Karakterin nesnelere dokunurken veya zemine basarken daha gerçekçi görünmesi için IK teknolojilerini uyguladım. Bu sayede karakterin ellerinin ve ayaklarının çevreyle olan teması, animasyonların ötesinde dinamik ve fiziksel bir tutarlılık kazandı.

**MetaHuman Entegrasyonu**  
Epic Games MetaHuman teknolojisi ile oluşturulan karakterlerin yüksek sadakatli görsel yapısını, oyun içi mekaniklerle (bakış takibi, mimik etkileşimleri vb.) birleştirerek daldırıcılığı (immersion) artırdım.

## Öne Çıkan Özellikler

- **Deneyim Odaklı Öğrenme:** Sınav yapmaz, fiziksel ve zihinsel refleks kazandırır
- **Psikolojik Güven:** Travmatize edici sahnelerden kaçınılarak, "Ben bunu başarabilirim" hissi uyandıran kontrollü bir gerilim yapısı sunar
- **Teknik Mimari:** Unreal Engine 5'in gücüyle, yüksek kaliteli görsellik ve optimize edilmiş etkileşim mekaniklerini bir araya getirir

## Ekran Görüntüleri

<div class="image-slider">
    <div class="slider-wrapper">
        <img src="/images/proje-2/screenshot1.jpg" alt="Ekran Görüntüsü 1" class="slide active">
        <img src="/images/proje-2/screenshot2.jpg" alt="Ekran Görüntüsü 2" class="slide">
    </div>
    <button class="slider-btn prev" onclick="moveSlide(-1)">‹</button>
    <button class="slider-btn next" onclick="moveSlide(1)">›</button>
    <div class="slider-dots">
        <span class="dot active" onclick="goToSlide(0)"></span>
        <span class="dot" onclick="goToSlide(1)"></span>
    </div>
</div>

<script>
let slideIndex = 0;

function moveSlide(n) {
    const slides = document.querySelectorAll('.slide');
    const dots = document.querySelectorAll('.dot');
    
    slides[slideIndex].classList.remove('active');
    dots[slideIndex].classList.remove('active');
    
    slideIndex = (slideIndex + n + slides.length) % slides.length;
    
    slides[slideIndex].classList.add('active');
    dots[slideIndex].classList.add('active');
}

function goToSlide(n) {
    const slides = document.querySelectorAll('.slide');
    const dots = document.querySelectorAll('.dot');
    
    slides[slideIndex].classList.remove('active');
    dots[slideIndex].classList.remove('active');
    
    slideIndex = n;
    
    slides[slideIndex].classList.add('active');
    dots[slideIndex].classList.add('active');
}
</script>

<style>
.image-slider {
    position: relative;
    width: 100%;
    max-width: 1200px;
    margin: 3rem auto;
    border-radius: 15px;
    overflow: hidden;
    background: rgba(0, 0, 0, 0.3);
}

.slider-wrapper {
    position: relative;
    width: 100%;
    height: 600px;
}

.slide {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    object-fit: cover;
    opacity: 0;
    transition: opacity 0.5s ease-in-out;
}

.slide.active {
    opacity: 1;
}

.slider-btn {
    position: absolute;
    top: 50%;
    transform: translateY(-50%);
    background: rgba(0, 212, 255, 0.7);
    color: white;
    border: none;
    width: 50px;
    height: 50px;
    font-size: 2rem;
    cursor: pointer;
    border-radius: 50%;
    transition: all 0.3s ease;
    z-index: 10;
    display: flex;
    align-items: center;
    justify-content: center;
    line-height: 1;
}

.slider-btn:hover {
    background: #00d4ff;
    transform: translateY(-50%) scale(1.1);
}

.slider-btn.prev {
    left: 20px;
}

.slider-btn.next {
    right: 20px;
}

.slider-dots {
    position: absolute;
    bottom: 20px;
    left: 50%;
    transform: translateX(-50%);
    display: flex;
    gap: 10px;
    z-index: 10;
}

.dot {
    width: 12px;
    height: 12px;
    border-radius: 50%;
    background: rgba(255, 255, 255, 0.5);
    cursor: pointer;
    transition: all 0.3s ease;
}

.dot.active {
    background: #00d4ff;
    width: 30px;
    border-radius: 6px;
}

@media (max-width: 768px) {
    .slider-wrapper {
        height: 400px;
    }
    
    .slider-btn {
        width: 40px;
        height: 40px;
        font-size: 1.5rem;
    }
}
</style>

## Demo Video

<div style="position: relative; width: 100%; max-width: 1200px; margin: 3rem auto; padding-bottom: 56.25%; height: 0; overflow: hidden; border-radius: 15px; box-shadow: 0 10px 40px rgba(0, 212, 255, 0.3);">
    <iframe 
        style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; border: 0; border-radius: 15px;" 
        src="https://drive.google.com/file/d/1y1f6PZE3QkpzqiNI_okDM666TnkxDoIz/preview" 
        allowfullscreen 
        allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture">
    </iframe>
</div>

---

*Son güncelleme: Ocak 2026*


