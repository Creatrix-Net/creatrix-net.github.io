---
layout: post
date: 2025-07-04 00:00:00-0000
inline: false
related_posts: false
title: Complete Overhaul - fluxpoint.py v0.2.0 Brings Structured, Async-First Design
---

## 🔖 fluxpoint.py v0.2.0 – Release Notes

### 🚀 Overview

This version marks a major overhaul of the `fluxpoint.py` library, aligning it closely with the [[official Fluxpoint API](https://docs.fluxpoint.dev/api)](https://docs.fluxpoint.dev/api) and introducing cleaner structure, richer endpoint support, and better developer experience.

---

### ✨ Highlights

* ✅ **Modular Restructuring**: The entire library has been split into clearly defined modules based on endpoint categories such as `Convert`, `Color`, `Minecraft`, `Utility`, `ImageGen`, and more.
* ⚙️ **Complete API Coverage**: The wrapper now supports nearly all documented endpoints including:

  * `/convert`
  * `/color`
  * `/mc`
  * `/utility`
  * `/image-gen/custom-image`
  * `/image-gen/templates`
  * `/sfw` and `/nsfw` images & gifs
* 📦 **Dynamic Versioning**: The version is now updated internally and reflected dynamically in requests.
* 📚 **Rebranded Documentation**:

  * Moved under the new namespace: `Creatrix-Net`
  * ReadTheDocs link updated: [[fluxpointpy.dhruvashaw.in](https://fluxpointpy.dhruvashaw.in/en/latest/)](https://fluxpointpy.dhruvashaw.in/en/latest/)

---

### 🔧 Changes & Improvements

#### 🧱 Structural

* Refactored project from monolithic classes to modular endpoint-driven structure.
* Introduced new directories: `paths/`, `vars.py`, etc.
* Deleted legacy files like `enums.py`, `images.py`, `gifs.py`, and `nsfw.py`.

#### 🖼️ Image Generation

* Split `ImageGenerator` into:

  * `CustomImage`: For fully customizable graphics using `images`, `texts`, colors, dimensions.
  * `Template`: For template-based welcome images.

#### 🌈 New Features

* **Color API**:

  * `random()` – fetch random colors
  * `info()` – fetch color info by name, hex, or RGB

* **Convert API**:

  * HTML ↔ Markdown
  * Image format conversion (`png`, `webp`, `jpg`) with quality settings

* **Minecraft API**:

  * Ping server, get player UUID, retrieve skins with `SkinType`

* **Utility API**:

  * Convert Unix timestamp / Discord snowflake to human-readable formats

* **List API**:

  * Fetch lists of available banners, icons, fonts

* **Tests API**:

  * Provides endpoints to validate API, images, JSON, gallery, and error handling

---

### 🐛 Fixes & Minor Updates

* Fixed hardcoded API links in examples & README.
* Improved Windows compatibility with proper asyncio event loop policies.
* Updated installation instructions for Python ≥ 3.9.
* Cleaned up and replaced outdated or incorrect references and examples.

---

### 🧪 Examples Refreshed

* Simplified and tested examples across:

  * `simple_request.py`
  * `custom_generator_test.py`
  * `welcome_image.py`
* Examples now match the refactored client interface.

---

### 📚 Documentation

Updated to reflect all new classes, methods, and expected outputs. See the full docs at:
👉 [https://fluxpointpy.dhruvashaw.in/en/latest/](https://fluxpointpy.dhruvashaw.in/en/latest/)

---

### 👥 Contributors

* [[@Dhruvacube](https://github.com/Dhruvacube)](https://github.com/Dhruvacube) (Author)
* [[@Creatrix-Net](https://github.com/Creatrix-Net)](https://github.com/Creatrix-Net) (Organization)

**Full Changelog**: https://github.com/Creatrix-Net/fluxpoint.py/compare/v0.1.1...v0.2.0


That's it `` ¯\_(ツ)_/¯``
