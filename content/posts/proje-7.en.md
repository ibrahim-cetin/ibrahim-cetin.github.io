+++
date = '2026-01-01T10:00:00+03:00'
draft = false
title = 'Monochrom'
tags = ["Unity", "Game Jam", "State Machine"]
categories = ["Game Development"]
featured_image = "/images/proje-7/cover.jpg"
+++

**Monochrom** tells the story of an adventure where the main character's shadow is trapped in darkness, and the character uses light as a tool to reclaim their shadow. Shaped around the question **"Who are you in the dark, what are you in the light?"**, the game forces players to constantly transition between two different states of being.

## Game Mechanics and Concept

The core loop of the game is built on how light and darkness change the character's controllable form:

**Duality System:** While the player moves with their own body in bright areas, they begin to control their trapped shadow when entering dark regions.

**Room Illumination:** The main objective is to illuminate rooms in levels with the right strategy to free the shadow and help the character reach wholeness.

**Minimalist Approach:** With a design philosophy away from complexity and focused on mechanics, the player is enabled to focus directly on "interaction with light."

## Technical Implementation and Development Process

As a **Game Jam** project, speed and clean code architecture were prioritized during Monochrom's development:

### Dynamic Character State Management

A precise **"State Machine"** structure managing the character's transitions between light and dark areas. Through light sensors/trigger systems, the character's form (body or shadow) and the different abilities of these forms (jump height, movement speed, etc.) were enabled to change instantly.

### Light and Trigger Systems

I designed an **"Event-Based"** system that updates the state of physical obstacles and passages in the game world as rooms are illuminated. This way, when a lamp is turned on, not just a visual change occurs, but the opening or closing of new paths is managed optimally within the game's logic framework.

### Rapid Prototyping and Architecture

Under the 48-hour time constraint; thanks to modular and reusable code blocks, the game's core mechanics were made functional within the first 24 hours. During this process, an infrastructure was created that facilitates error management and allows quick testing of game balance (level design).

## Screenshots

<div class="image-slider">
    <div class="slider-wrapper">
        <img src="/images/proje-7/screenshot1.jpg" alt="Screenshot 1" class="slide active">
        <img src="/images/proje-7/screenshot2.jpg" alt="Screenshot 2" class="slide">
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
        Your browser does not support the video tag.
    </video>
</div>

---

*Last updated: January 2026*

