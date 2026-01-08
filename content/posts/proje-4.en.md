+++
date = '2026-01-04T10:00:00+03:00'
draft = false
title = 'VR 360° Interactive Tour Experience'
tags = ["Unity", "VR", "Scriptable Objects"]
categories = ["Game Development"]
featured_image = "/images/proje-4/cover.jpg"
+++

This project goes beyond traditional 360° photo tours, transforming static images into a dynamic and interactive **virtual reality (VR) experience**. Users navigate between spaces with Google Street View-like navigation while deeply interacting with objects in the environment.

## Project Overview

The primary goal of the project is to create an immersive exploration space within high-resolution 360° panoramic photos, enriched with objects that have real-world physical properties and sounds.

## Technical Architecture and Development Approach

The strongest aspect of the project is its completely **modular and scalable** code structure. I applied modern game development patterns during the software development process:

### 1. Data-Driven Architecture with Scriptable Objects

Every interactable object, every sound, and every scene transition was designed using **Scriptable Objects**. This enables:

- Creating new content by **simply defining data** (through the Inspector) without needing to write code for adding new interactive objects
- Optimized memory management with the **"single source of truth"** principle applied throughout the project

### 2. State Machine Management

I built a **State Machine** structure to manage complex interactions (e.g., object examination moments, sound playback states, scene transition effects).

- This structure prevented the code from becoming spaghetti and ensured each state (Idle, Interacting, Transition, etc.) operates isolated and error-free

### 3. Event-Based Interaction

I designed an **Event-Bus** or **Unity Events** based structure to minimize coupling between systems.

- When an object is touched; sound system, visual effects, and data recording systems are triggered independently from each other
- This makes project maintenance and adding new features extremely easy

## Interactive and Spatial Experience

**Modular Object Properties**  
Each object's unique weight, texture, and info card properties are coded modularly.

**Spatial Audio**  
When interacting with objects, sounds are triggered in 3D according to their positions in the VR environment, maximizing the sense of realism.

**VR Navigation**  
A teleportation and transition system that provides smooth transitions between 360° images, preventing motion sickness and user fatigue.

## Conclusion

This work is not just a VR tour, but also a proof of how complex systems can be architecturally transformed into clean, modular, and performant structures. The project has an infrastructure that can be adapted in seconds to many different fields, from **corporate training simulations to virtual museum tours**.

## Screenshots

<div class="image-slider">
    <div class="slider-wrapper">
        <img src="/images/proje-4/screenshot1.jpg" alt="Screenshot 1" class="slide active">
        <img src="/images/proje-4/screenshot2.jpg" alt="Screenshot 2" class="slide">
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

*Last updated: January 2026*


