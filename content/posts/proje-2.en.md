+++
date = '2026-01-06T10:00:00+03:00'
draft = false
title = 'Panik Yok (No Panic)'
tags = ["Unreal Engine", "MetaHuman", "IK System"]
categories = ["Game Development"]
featured_image = "/images/proje-2/cover.jpg"
+++

**Panik Yok (No Panic)** is an interactive educational game that integrates children and young people into a decision-making mechanism rather than just theoretically explaining what they should do during disasters. Launched with the motto **"We don't teach, we let them experience,"** this project aims to turn disaster awareness from memorization into a reflex.

## Project Vision

Unlike traditional educational methods, **Panik Yok** guides players with curiosity and awareness, not fear and stress. Wrong decisions in the game do not result in a "Game Over" screen; instead, they teach why that decision was wrong and its real-life consequences.

## Scenario and Gameplay

In this version, we simulated an earthquake moment in a school and the subsequent evacuation process. The player makes dynamic choices as **Volunteer Firefighter Mert** and directs students to safe evacuation routes.

## My Technical Contributions and Development Process

During the development phase of the project, I focused on game mechanics and character-environment interaction using the Unreal Engine ecosystem:

**Interactive Object System**  
I designed a flexible and modular interaction system that allows the player to interact with doors, fire extinguishers, and evacuation equipment in the environment in real-time.

**IK (Inverse Kinematics) Character Animations**  
I applied IK technologies to make the character look more realistic when touching objects or stepping on the ground. This gave the character's hands and feet a dynamic and physical consistency beyond animations.

**MetaHuman Integration**  
I increased immersion by combining the high-fidelity visual structure of characters created with Epic Games MetaHuman technology with in-game mechanics (gaze tracking, facial interactions, etc.).

## Key Features

- **Experience-Based Learning:** Does not test, but provides physical and mental reflexes
- **Psychological Safety:** Avoids traumatic scenes and offers a controlled tension structure that evokes the feeling "I can do this"
- **Technical Architecture:** Combines high-quality visuals and optimized interaction mechanics with the power of Unreal Engine 5

## Screenshots

<div class="image-slider">
    <div class="slider-wrapper">
        <img src="/images/proje-2/screenshot1.jpg" alt="Screenshot 1" class="slide active">
        <img src="/images/proje-2/screenshot2.jpg" alt="Screenshot 2" class="slide">
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

*Last updated: January 2026*


