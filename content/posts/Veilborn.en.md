+++
date = '2026-01-07T16:14:07+03:00'
draft = false
title = 'Veilborn'
tags = ["2D", "Vector Art", "Narrative Adventure"]
categories = ["Game Development"]
featured_image = "/images/veilborn/cover.jpg"
+++

## ARAF INTERACTIVE – Veilborn

*"Here, you see as much as you can imagine."*

**Veilborn** is a **2D narrative adventure** with a vector art style, set in the surreal and fragmented mental world of a patient in a coma.

## Story

After an accident, you wake up in a strange world. This is the limbo between consciousness and nothingness; a mental landscape where past, present, and future intertwine. Here, the loved ones you forgot are mere whispers, the hatreds you suppressed and your deepest fears are nightmares embodied in flesh. Among these fragmented memories, you must find your way and reshape your past.

**Before you wake up, will you have a story worth remembering?**

## About the Game

Veilborn invites the player into the depths of a comatose patient's mind. In this journey built on piecing together fragmented memories, confronting traumas, and questioning the boundaries of reality, atmosphere-focused storytelling is at the center. The player progresses through sections representing different memories with action, puzzle, platform, and exploration mechanics.

## Gameplay

Veilborn combines its atmospheric story with fluid and dynamic gameplay. In the mind of a comatose patient, you'll progress through sections that each offer different challenges.

**EXPLORE:** Discover surreal worlds, each with its own theme, containing fragmented memories and hidden secrets.

**FIGHT & SOLVE:** Battle enemies representing your traumas or use your intelligence to solve cleverly designed environmental puzzles.

**JUMP & ESCAPE:** Overcome challenging platform sections with precise controls and escape from the most dangerous corners of your mind.

**SHAPE:** Shape the flow of the story and your relationship with your past through meaningful decisions.

## Key Features

**Deep and Atmospheric Story**  
An emotional and mysterious scenario that draws players in with dialogue narration and environmental storytelling techniques.

**Unique Vector Art Style**  
An unforgettable visual world created with minimalist yet impressive, sharp-lined vector graphics.

**Dynamic Gameplay**  
Mechanics that change in each section and serve the story. A diverse experience ranging from calm puzzles to tense escape sequences.

**Impressive Music and Sound Design**  
Carefully composed music and sound effects that strengthen the game's melancholic and surreal atmosphere.

## Project Information

**Studio:** Araf Interactive  
**Genre:** 2D Narrative Adventure, Action, Puzzle-Platformer  
**Platform:** PC (Steam)  
**Target Audience:** Players who love narrative-focused and artistic games (16+)  
**Current Status:** Playable Demo Ready  
**Planned Event:** Steam Next Fest - October 2025

## Inspirations

- **Katana Zero** (Action sequences, environmental mechanics)
- **Gris** (Artistic narration, emotional depth)
- **Limbo / Inside** (Atmosphere, environmental puzzles)
- **Celeste** (Platform mechanics integrated with story)

## About the Team

**Araf Interactive** is a passionate and dedicated independent team of 3 people based in Konya. We combine our talents from different disciplines to offer players unforgettable and thought-provoking experiences.

- **İbrahim ÇETİN** - Game Design, Software Development
- **Eren DAĞ** - Level Design
- **Nurben ACAR** - Story, Art Design

## Screenshots

<div class="image-slider">
    <div class="slider-wrapper">
        <img src="/images/veilborn/screenshot1.jpg" alt="Screenshot 1" class="slide active">
        <img src="/images/veilborn/screenshot2.jpg" alt="Screenshot 2" class="slide">
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

*Last updated: January 2026*

