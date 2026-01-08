+++
date = '2026-01-01T10:00:00+03:00'
draft = false
title = 'Monochrom'
tags = ["Unity", "Game Jam", "State Machine"]
categories = ["Oyun Geliştirme"]
featured_image = "/images/proje-7/cover.jpg"
+++

**Monochrom**, ana karakterin gölgesinin karanlıkta hapsolduğu ve karakterin gölgesini geri kazanmak için ışığı bir araç olarak kullandığı bir serüveni konu alır. **"Karanlıkta kimsin, aydınlıkta nesin?"** sorusu etrafında şekillenen oyun, oyuncuyu iki farklı varlık durumu arasında sürekli bir geçiş yapmaya zorlar.

## Oyun Mekaniği ve Konsept

Oyunun temel döngüsü, ışık ve karanlığın karakterin kontrol edilebilir formunu değiştirmesi üzerine kuruludur:

**Dualite Sistemi:** Oyuncu, aydınlık alanlarda kendi bedeniyle hareket ederken; karanlık bölgelere geçtiğinde hapsolmuş gölgesini kontrol etmeye başlar.

**Oda Aydınlatma:** Seviyelerdeki odaları doğru stratejiyle aydınlatarak gölgeyi özgürlüğüne kavuşturmak ve karakteri bütününe ulaştırmak temel amaçtır.

**Minimalist Yaklaşım:** Karmaşadan uzak, mekanik odaklı bir tasarım anlayışıyla oyuncunun doğrudan "ışıkla etkileşime" odaklanması sağlanmıştır.

## Teknik Uygulama ve Geliştirme Süreci

Bir **Game Jam** projesi olması sebebiyle, Monochrom'un geliştirilme sürecinde hız ve temiz kod mimarisi ön planda tutulmuştur:

### Dinamik Karakter Durum Yönetimi (State Management)

Karakterin aydınlık ve karanlık bölgeler arasındaki geçişlerini yöneten hassas bir **"State Machine"** yapısı. Işık sensörleri/trigger sistemleri aracılığıyla karakterin hangi formda (beden veya gölge) olacağı ve bu formların sahip olduğu farklı yeteneklerin (zıplama yüksekliği, hareket hızı vb.) anlık olarak değişmesi sağlandı.

### Işık ve Tetikleyici Sistemleri

Odaların aydınlatılmasıyla birlikte oyun dünyasındaki fiziksel engellerin ve geçitlerin durumunu güncelleyen bir **"Event-Based"** (olay tabanlı) sistem tasarladım. Bu sayede bir lamba açıldığında sadece görsel bir değişim değil, oyunun mantık çerçevesinde (logic) yeni yolların açılması veya kapanması optimize bir şekilde yönetildi.

### Hızlı Prototipleme ve Mimari

48 saatlik süre kısıtlaması altında; modüler ve tekrar kullanılabilir kod blokları sayesinde oyunun temel mekanikleri ilk 24 saat içerisinde çalışır hale getirilmiştir. Bu süreçte, hata yönetimini kolaylaştıran ve oyun dengesini (level design) hızlıca test etmeye olanak tanıyan bir altyapı oluşturulmuştur.

## Ekran Görüntüleri

<div class="image-slider">
    <div class="slider-wrapper">
        <img src="/images/proje-7/screenshot1.jpg" alt="Ekran Görüntüsü 1" class="slide active">
        <img src="/images/proje-7/screenshot2.jpg" alt="Ekran Görüntüsü 2" class="slide">
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
        poster="/images/proje-7/screenshot1.jpg">
        <source src="/images/proje-7/video.mp4" type="video/mp4">
        Tarayıcınız video etiketini desteklemiyor.
    </video>
</div>

---

*Son güncelleme: Ocak 2026*

