+++
date = '2026-01-07T16:14:07+03:00'
draft = false
title = 'Veilborn'
tags = ["2D", "Vector Art", "Narrative Adventure"]
categories = ["Oyun Geliştirme"]
featured_image = "/images/veilborn/cover.jpg"
+++

## ARAF INTERACTIVE – Veilborn

*"Burada hayal ettiğiniz kadarını görürsünüz."*

**Veilborn**, komadaki bir hastanın sürreal ve parçalanmış zihin dünyasında geçen, vektör sanat tarzına sahip bir **2D anlatı macerasıdır**.

## Hikaye

Geçirdiğin bir kazanın ardından yabancı bir dünyaya uyanıyorsun. Burası, bilincin ve hiçliğin arafı; geçmişin, şimdinin ve geleceğin iç içe geçtiği bir zihin manzarası. Burada unuttuğun sevdiklerin birer fısıltı, bastırdığın nefretler ve en derin korkuların ise ete kemiğe bürünmüş birer kabustur. Bu parçalanmış anıların arasında yolunu bulmalı, geçmişini yeniden şekillendirmelisin. 

**Uyanmadan önce, hatırlanmaya değer bir hikayen kalacak mı?**

## Oyun Hakkında

Veilborn, oyuncuyu komadaki bir hastanın zihninin derinliklerine davet eder. Parçalanmış anıları birleştirme, travmalarla yüzleşme ve gerçekliğin sınırlarını sorgulama üzerine kurulu bu yolculukta, atmosfer odaklı bir hikaye anlatımı merkezdedir. Oyuncu, her biri farklı bir anıyı temsil eden bölümlerde aksiyon, bulmaca, platform ve keşif mekanikleriyle ilerler.

## Oynanış

Veilborn, atmosferik hikayesini akıcı ve dinamik bir oynanışla birleştirir. Komadaki bir hastanın zihninde, her biri farklı bir mücadele sunan bölümlerde ilerleyeceksin.

**KEŞFET:** Parçalanmış anıları ve gizli sırları barındıran, her biri kendi temasına sahip sürreal dünyaları keşfet.

**SAVAŞ & ÇÖZ:** Travmalarını temsil eden düşmanlarla savaş veya zekanı kullanarak zekice tasarlanmış çevresel bulmacaları çöz.

**ZIPLA & KAÇ:** Hassas kontrollerle zorlu platform bölümlerinin üstesinden gel ve zihninin en tehlikeli köşelerinden kaç.

**ŞEKİLLENDİR:** Vereceğin anlamlı kararlarla hikayenin akışını ve geçmişinle olan ilişkini şekillendir.

## Öne Çıkan Özellikler

**Derin ve Atmosferik Hikaye**  
Diyaloglu anlatım ve çevresel hikaye anlatımı teknikleriyle oyuncuyu içine çeken, duygusal ve gizemli bir senaryo.

**Özgün Vektör Sanat Tarzı**  
Minimalist ama etkileyici, keskin hatlara sahip vektör grafikleriyle yaratılmış unutulmaz bir görsel dünya.

**Dinamik Oynanış**  
Her bölümde değişen, hikayeye hizmet eden mekanikler. Sakin bulmacalardan gerilimli kaçış sekanslarına uzanan çeşitli bir deneyim.

**Etkileyici Müzik ve Ses Tasarımı**  
Oyunun melankolik ve sürreal atmosferini güçlendiren, özenle bestelenmiş müzikler ve ses efektleri.

## Proje Bilgileri

**Stüdyo:** Araf Interactive  
**Tür:** 2D Anlatı Macerası, Aksiyon, Puzzle-Platformer  
**Platform:** PC (Steam)  
**Hedef Kitle:** Anlatı odaklı ve sanatsal oyunları seven oyuncular (16+)  
**Mevcut Durum:** Oynanabilir Demo Hazır  
**Planlanan Etkinlik:** Steam Next Fest - Ekim 2025

## İlham Kaynakları

- **Katana Zero** (Aksiyon sekansları, çevre mekanikleri)
- **Gris** (Sanatsal anlatım, duygusal derinlik)
- **Limbo / Inside** (Atmosfer, çevresel bulmacalar)
- **Celeste** (Hikaye ile bütünleşen platform mekanikleri)

## Ekip Hakkında

**Araf Interactive**; Konya merkezli, 3 kişilik tutkulu ve adanmış bağımsız bir ekiptir. Farklı disiplinlerden gelen yeteneklerimizi, oyunculara unutulmaz ve düşündürücü deneyimler sunmak için birleştiriyoruz.

- **İbrahim ÇETİN** - Game Design, Yazılım
- **Eren DAĞ** - Level Design
- **Nurben ACAR** - Hikaye, Sanat Tasarımı

## Ekran Görüntüleri

<div class="image-slider">
    <div class="slider-wrapper">
        <img src="/images/veilborn/screenshot1.jpg" alt="Ekran Görüntüsü 1" class="slide active">
        <img src="/images/veilborn/screenshot2.jpg" alt="Ekran Görüntüsü 2" class="slide">
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
        src="https://www.youtube.com/embed/-MYr7L_LTMk" 
        allowfullscreen 
        allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture">
    </iframe>
</div>

---

*Son güncelleme: Ocak 2026*
