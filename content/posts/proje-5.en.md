+++
date = '2026-01-03T10:00:00+03:00'
draft = false
title = 'VR Room Configurator'
tags = ["Unity", "VR", "Grid System"]
categories = ["Game Development"]
featured_image = "/images/proje-5/cover.jpg"
+++

This project offers users the opportunity to design **fully modular and customizable living spaces** in a virtual reality environment as an interior architecture and decoration simulation. Users can build a room from scratch, furnish it as they wish, and personalize the design with material choices.

## Project Overview

The project combines complex placement algorithms with VR's immersive world. Working like a furniture store or interior architecture solution tool, the system enables users to create professional designs within a limited area (Grid).

## Technical Highlights

### 1. Dynamic Grid-Based Placement System

The room creation process is built on a scalable grid base such as 10x10.

**Precise Placement:** Thanks to the "Snap" system that ensures objects fit perfectly into grid cells, millimeter precision is achieved in placements made with VR controllers.

**Procedural Room Creation:** Users can dynamically change wall and floor structure according to the selected room type.

### 2. Runtime Object and Material Customization

Instead of static models in-game, a completely dynamic structure has been designed:

**Panel-Based Interaction:** Access to the furniture library is provided through spatial UI panels integrated into the VR environment.

**Instant Material Change:** Materials such as fabric, wood, or metal of selected furniture can be changed during Runtime. This system is optimized in a performance-friendly way using Shader and Material Property blocks.

### 3. VR UX and Spatial UI

**User-Friendly Interface:** Ergonomic menu designs that don't disrupt depth perception in VR and don't tire the user.

**Intuitive Controls:** Holding, rotating, and placing objects are provided with natural interactions (Grabbing & Raycasting) optimized for VR controllers.

## Use Cases

- **E-Commerce:** Virtual store experience for furniture brands
- **Real Estate:** Interactive floor plan presentation for projects not yet built
- **Education:** Scaled design practices for interior architecture students

## Source Code and Development Process

You can access all the technical infrastructure, modular code structure, and implementation details of the project on GitHub.

**Project GitHub Repository:** [github.com/ibrahim-cetin/VR_Room_Design](https://github.com/ibrahim-cetin/VR_Room_Design)

---

*Last updated: January 2026*


