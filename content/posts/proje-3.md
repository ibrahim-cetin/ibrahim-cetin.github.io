+++
date = '2026-01-05T10:00:00+03:00'
draft = false
title = 'Silent Gun'
tags = ["Unity", "C#", "Game Jam"]
categories = ["Oyun Geliştirme"]
featured_image = "/images/proje-3/cover.jpg"
+++

**Silent Gun**, Global Game Jam 2025 etkinliğinde **Floppy Disk** ekibiyle birlikte Unity kullanılarak geliştirilen dinamik bir oyun projesidir. Oyuncu, her biri benzersiz efektler ve oynanış mekanikleri sunan farklı mermi türleri arasında geçiş yapabileceği bir silah ve mermi (balon) sistemine sahiptir.

## Oyun Hakkında

Silent Gun, elementel güçleri stratejik olarak kullanan, hızlı tempolu bir aksiyon oyunudur. Oyuncular, Ateş, Su ve Buz olmak üzere üç farklı mermi türü arasında geçiş yaparak çevresel bulmacaları çözer ve düşmanları alt ederler. Her element, oyun dünyasıyla farklı şekillerde etkileşime girer ve oyunculara taktiksel derinlik kazandırır.

## Öne Çıkan Özellikler

**Silah Nişan Alma Sistemi**  
Silah, oyuncunun imlecini yumuşak bir şekilde takip ederek doğru açıda hizalanır ve sürükleyici bir nişan alma deneyimi sunar.

**Elementel Mermi Modları**  
Oyuncular Ateş, Su ve Buz olmak üzere üç farklı elementel atış türü arasında geçiş yapabilir. Her biri kendine özgü görsel efektler ve etkileşimlere sahiptir.

**Animasyon Yönetimi**  
Silah animasyonları tetikleyiciler kullanılarak kontrol edilir, bu sayede akıcı geçişler ve geribildirimler sağlanır.

**Mermi Etkileşimleri**  
Her mermi, belirli efektleri tetiklemek için çevresel nesnelerle etkileşime girer ve oyuna derinlik ve strateji katar.

**Element Animasyonları**  
Mermi türleri arasındaki görsel geçişler, detaylı animasyonlarla zenginleştirilmiştir.

**Fizik Tabanlı Hareket**  
Mermiler, gerçekçi ve fizik odaklı hareket için Rigidbody2D kullanır.

**Etkileşim Sistemi**  
IInteractable arayüzünü uygulayarak, mermilerin farklı nesnelere bağlamsal olarak yanıt vermesini sağlar.

**GameManager Entegrasyonu**  
BlackBoard sistemi kullanarak Game Manager ile iletişim kurar, merkezi kontrol ve mantık akışını garanti eder.

## Teknik Detaylar

- **Motor:** Unity Engine
- **Programlama:** C#
- **Fizik Sistemi:** Rigidbody2D
- **Tasarım Deseni:** Interface-based Interaction System
- **Mimari:** BlackBoard Pattern ile merkezi yönetim

## Global Game Jam 2025

Bu proje, dünyanın en büyük oyun geliştirme etkinliklerinden biri olan **Global Game Jam 2025**'te 48 saat içinde geliştirilmiştir. Floppy Disk ekibi olarak, sınırlı zaman içinde dinamik mekanikler ve yaratıcı çözümler üretmenin zorluklarıyla başa çıktık.

## Ekran Görüntüleri

<div class="image-slider">
    <div class="slider-wrapper">
        <img src="/images/proje-3/screenshot1.jpg" alt="Ekran Görüntüsü 1" class="slide active">
        <img src="/images/proje-3/screenshot2.jpg" alt="Ekran Görüntüsü 2" class="slide">
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

<div style="width: 100%; max-width: 1200px; margin: 3rem auto; border-radius: 15px; overflow: hidden; box-shadow: 0 10px 40px rgba(0, 212, 255, 0.3);">
    <video 
        style="width: 100%; height: auto; display: block; border-radius: 15px;" 
        controls 
        preload="metadata"
        poster="/images/proje-3/screenshot1.jpg">
        <source src="/images/proje-3/video.mp4" type="video/mp4">
        Tarayıcınız video etiketini desteklemiyor.
    </video>
</div>

---

*Son güncelleme: Ocak 2026*


