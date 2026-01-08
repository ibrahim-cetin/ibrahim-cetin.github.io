+++
date = '2026-01-05T10:00:00+03:00'
draft = false
title = 'Silent Gun'
tags = ["Unity", "C#", "Game Jam"]
categories = ["Game Development"]
featured_image = "/images/proje-3/cover.jpg"
+++

**Silent Gun** is a dynamic game project developed using Unity in collaboration with the **Floppy Disk** team during Global Game Jam 2025. It features a weapon and projectile (bubble) system that allows players to switch between different ammo types — each with unique effects and gameplay mechanics.

## About the Game

Silent Gun is a fast-paced action game that strategically utilizes elemental powers. Players switch between three different projectile types — Fire, Water, and Ice — to solve environmental puzzles and defeat enemies. Each element interacts with the game world in different ways, providing tactical depth to players.

## Key Features

**Weapon Aiming System**  
The weapon smoothly rotates to follow the player's cursor, aligning at the correct angle for an immersive aiming experience.

**Elemental Ammo Modes**  
Players can switch between three elemental shot types — Fire, Water, and Ice — each with distinct visual effects and interactions.

**Animation Management**  
Weapon animations are controlled using triggers, ensuring smooth transitions and responsive feedback.

**Projectile Interactions**  
Each projectile interacts with environmental objects to trigger specific effects, adding depth and strategy to gameplay.

**Elemental Animations**  
Visual transitions between ammo types are enhanced through detailed and polished animations.

**Physics-Based Movement**  
Projectiles utilize Rigidbody2D for realistic, physics-driven motion.

**Interaction System**  
Implements the IInteractable interface, allowing projectiles to respond contextually to different objects in the environment.

**GameManager Integration**  
Uses a BlackBoard system to communicate with the Game Manager, ensuring centralized control and seamless logic flow.

## Technical Details

- **Engine:** Unity Engine
- **Programming:** C#
- **Physics System:** Rigidbody2D
- **Design Pattern:** Interface-based Interaction System
- **Architecture:** Centralized management with BlackBoard Pattern

## Global Game Jam 2025

This project was developed during **Global Game Jam 2025**, one of the world's largest game development events, within a 48-hour timeframe. As the Floppy Disk team, we tackled the challenges of creating dynamic mechanics and creative solutions under tight time constraints.

## Screenshots

<div class="image-slider">
    <div class="slider-wrapper">
        <img src="/images/proje-3/screenshot1.jpg" alt="Screenshot 1" class="slide active">
        <img src="/images/proje-3/screenshot2.jpg" alt="Screenshot 2" class="slide">
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
        Your browser does not support the video tag.
    </video>
</div>

---

*Last updated: January 2026*


