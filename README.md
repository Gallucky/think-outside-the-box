# Think Outside the Box

A pixel-perfect HTML & CSS implementation of a professional services / consulting landing page Figma UI design, built with a structured SASS architecture using variables, mixins, and modular partials.

![Project Preview](./images/project_preview.png)

---

## Table of Contents

- [Overview](#overview)
- [Demo](#demo)
- [Tech Stack](#tech-stack)
- [Project Structure](#project-structure)
- [Getting Started](#getting-started)
- [SASS Architecture](#sass-architecture)
- [Design Reference](#design-reference)
- [Responsive Design](#responsive-design)
- [License](#license)

---

## Overview

Think Outside the Box is a UI implementation exercise faithfully translated from a Figma design. The page includes a hero section, service cards, a contact form, an embedded Google Map, and a social media contact bar. The project highlights a disciplined SASS architecture — with dedicated files for variables, colors, and reusable mixins — compiled to a single CSS output.

---

## Demo

Open `index.html` directly in any modern browser — no build step is required to view the project.

> To modify styles, edit the `.scss` source files and recompile. See [Getting Started](#getting-started) below.

---

## Tech Stack

| Technology | Purpose |
|---|---|
| HTML5 | Semantic page structure |
| CSS3 | Compiled style output |
| SASS (SCSS) | CSS preprocessing: variables, mixins, nesting, partials |
| Google Fonts | Custom web font (Heebo) |

---

## Project Structure

```
think-outside-the-box/
├── index.html
│
├── style/
│   ├── think_outside_the_box.scss      # Main stylesheet — imports all partials
│   ├── think_outside_the_box.css       # Compiled CSS output (do not edit directly)
│   └── think_outside_the_box.css.map   # Source map for debugging
│
├── colors/
│   ├── colors.scss                     # Global color variables
│   ├── colors.css
│   └── colors.css.map
│
├── variables/
│   ├── vars.scss                       # Global size & spacing variables
│   ├── vars.css
│   └── vars.css.map
│
├── mixins/
│   ├── flex.scss                       # Flexbox layout mixins
│   ├── border.scss                     # Border utility mixins
│   ├── position.scss                   # Positioning mixins (z-index helpers)
│   ├── margins_paddings.scss           # Reset and spacing mixins
│   └── *.css / *.css.map               # Compiled outputs and source maps
│
└── images/
    ├── project_preview.png
    ├── open_box.svg                    # Hero illustration
    ├── business_suitcase.png           # Service card icon
    ├── id_card.png                     # Service card icon
    ├── magic_wand.png                  # Service card icon
    ├── location.png                    # Map/contact section icon
    ├── phone.svg                       # Contact icon
    ├── facebook_f.svg                  # Social icon
    ├── instagram.svg                   # Social icon
    ├── linkedin_in.svg                 # Social icon
    └── icon_awesome_whatsapp.svg       # Floating WhatsApp icon + contact icon
```

---

## Getting Started

### View the Project

1. Clone or download the repository.
2. Open `index.html` in any modern browser. An internet connection is needed to load Google Fonts.

### Edit Styles

To modify the SASS source and recompile:

1. Install SASS globally if you haven't already:

```bash
npm install -g sass
```

2. Watch for changes and compile automatically:

```bash
sass --watch style/think_outside_the_box.scss style/think_outside_the_box.css
```

> **Important:** Always edit the `.scss` source files — never edit the compiled `.css` files directly, as your changes will be overwritten on the next compile.

---

## SASS Architecture

The project uses a modular SASS (SCSS) structure with clearly separated concerns:

### `colors/colors.scss` — Color Palette
Defines all color tokens used across the project:

```scss
$black: #000000;
$white: #ffffff;
$accent-color: #0ee1e1;
$section-card-bg-color: #f8f8f8;
$form-input-color: #e5eeff;
```

### `variables/vars.scss` — Size & Spacing Variables
Centralizes all dimension tokens for consistent sizing:

```scss
$full: 100%;
$form-input-width: 426px;
$form-input-height: 51px;
$contact-option-size: 95px;
// ... and more
```

### `mixins/` — Reusable Mixins

| File | Mixin(s) | Purpose |
|---|---|---|
| `flex.scss` | `flex-center`, `flex-col-center`, `flex-col-start`, `flex-col-reverse-center`, etc. | Flexbox layout shortcuts |
| `margins_paddings.scss` | `reset-element`, `fit-contents` | Global reset and sizing helpers |
| `position.scss` | `always-appear-on-top` | Z-index utility for overlays |
| `border.scss` | `test-border` | Debug/testing utility |

### `style/think_outside_the_box.scss` — Main Stylesheet
Imports all partials using `@use` and applies styles to all page sections. All component and layout styles live here.

---

## Design Reference

This project was implemented based on a Figma design. Key page sections include:

- **Hero** — headline, subtext, and SVG illustration with RTL text direction
- **Service Cards** — three icon-driven feature cards with accent background
- **Contact Form** — labeled inputs, textarea, and submit button with custom scrollbar styling
- **Google Map** — responsive embedded `<iframe>` alongside the contact form
- **Social Contact Bar** — circular icon links for WhatsApp, Facebook, Instagram, LinkedIn, and Phone
- **Floating WhatsApp Button** — fixed-position quick-contact icon (hidden on mobile)

---

## Responsive Design

The layout is fully responsive with a mobile breakpoint at `768px`. Each section has dedicated `@media (max-width: 768px)` rules, including:

- Column-reversed flex layouts on mobile
- Scaled-down typography and image sizes
- Adjusted form input dimensions
- Full-width cards and map on small screens
- Hidden floating WhatsApp button on mobile (`display: none`)

---

## License

This project is intended for educational and portfolio purposes.
