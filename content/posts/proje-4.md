+++
date = '2026-01-04T10:00:00+03:00'
draft = false
title = 'VR 360° Interaktif Tur Deneyimi'
tags = ["Unity", "VR", "Scriptable Objects"]
categories = ["Oyun Geliştirme"]
featured_image = "/images/proje-4/cover.jpg"
+++

Bu proje, geleneksel 360° fotoğraf turlarının ötesine geçerek, statik görüntüleri dinamik ve etkileşimli bir **sanal gerçeklik (VR) deneyimine** dönüştüren bir platformdur. Kullanıcılar Google Street View benzeri bir navigasyonla mekanlar arasında gezinirken, çevredeki nesnelerle derinlemesine etkileşime girebilirler.

## Proje Genel Bakış

Projenin temel amacı, yüksek çözünürlüklü 360° panoramik fotoğraflar içerisinde, gerçek dünya fiziksel özelliklerine ve seslerine sahip nesnelerle zenginleştirilmiş, daldırıcı (immersive) bir keşif alanı yaratmaktır.

## Teknik Mimari ve Geliştirme Yaklaşımı

Projenin en güçlü yönü, tamamen **modüler ve genişletilebilir (scalable)** bir kod yapısına sahip olmasıdır. Yazılım geliştirme sürecinde modern oyun geliştirme paternlerini uyguladım:

### 1. Scriptable Objects ile Veri Odaklı Mimari (Data-Driven)

Etkileşime geçilen her nesne, her ses ve her sahne geçişi **Scriptable Objects** kullanılarak tasarlandı. Bu sayede:

- Yeni etkileşimli nesneler eklemek için **kod yazmaya gerek kalmadan**, sadece veri tanımlayarak (Inspector üzerinden) yeni içerikler oluşturulabiliyor
- Bellek yönetimi optimize edildi ve projede **"single source of truth"** (tekil doğru kaynak) prensibi uygulandı

### 2. State Machine (Durum Makinesi) Yönetimi

Karmaşık etkileşimleri (Örn: Bir nesnenin incelenme anı, sesin çalma durumu, sahne arası geçiş efektleri) yönetmek için **State Machine** yapısını kurdum.

- Bu yapı, kodun spagettiye dönüşmesini engelledi ve her durumun (Idle, Interacting, Transition vb.) kendi içinde izole ve hatasız çalışmasını sağladı

### 3. Event-Based Interaction (Olay Tabanlı Etkileşim)

Sistemler arasındaki bağımlılığı (coupling) minimize etmek için **Event-Bus** veya **Unity Events** bazlı bir yapı kurguladım.

- Bir nesneye dokunulduğunda; ses sistemi, görsel efektler ve veri kaydedici sistemler birbirinden bağımsız olarak tetiklenir
- Bu, projenin bakımını ve yeni özellik eklenmesini son derece kolaylaştırır

## İnteraktif ve Mekansal Deneyim

**Modüler Nesne Özellikleri**  
Her nesnenin kendine has ağırlığı, dokusu ve bilgi kartı gibi özellikleri modüler olarak kodlandı.

**Spatial Audio (Mekansal Ses)**  
Nesnelerle etkileşime geçildiğinde sesler, VR ortamındaki konumlarına göre 3D olarak tetiklenir, bu da gerçekçilik hissini maksimize eder.

**VR Navigasyon**  
360° görseller arasında yumuşak geçişler sağlayan, kullanıcıyı yormayan (motion sickness önleyici) bir ışınlanma ve geçiş sistemi.

## Sonuç

Bu çalışma; sadece bir VR turu değil, aynı zamanda karmaşık sistemlerin nasıl temiz, modüler ve performanslı bir şekilde mimari haline getirilebileceğinin bir kanıtıdır. Proje, **kurumsal eğitim simülasyonlarından sanal müze gezilerine** kadar birçok farklı alana saniyeler içinde uyarlanabilecek bir altyapıya sahiptir.

## Ekran Görüntüleri

<div class="image-slider">
    <div class="slider-wrapper">
        <img src="/images/proje-4/screenshot1.jpg" alt="Ekran Görüntüsü 1" class="slide active">
        <img src="/images/proje-4/screenshot2.jpg" alt="Ekran Görüntüsü 2" class="slide">
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

---

*Son güncelleme: Ocak 2026*


