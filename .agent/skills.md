# KMCT Unified Website - AI Developer Instructions & Design System

## 1. Project Overview & Core Principles
* [cite_start]**Project:** KMCT Unified Website (9 colleges, 2 campuses: Kallanthode + Pooladikunnu)[cite: 30, 31].
* **Primary Goal:** Admissions conversion. [cite_start]This is NOT a brochure; it is a funnel[cite: 32, 33, 34].
* [cite_start]**Target Audience:** KEAM students, nursing aspirants, and parents across Kerala[cite: 36, 37].
* [cite_start]**Copywriting Rule:** "Every word earns its place or it gets cut." [cite: 39, 40] Do not generate fluffy, generic marketing text. Use direct, honest, and specific language.

## 2. Tech Stack & Architecture
* **Framework:** Astro (latest).
* **Styling:** Tailwind CSS **v4**. 
  * *Critical Rule for AI:* Tailwind v4 does NOT use `tailwind.config.mjs`. All custom variables (`@theme`) are located in `src/styles/global.css`. Do not attempt to create or modify a Tailwind config file.
* **Content Management:** Sanity CMS (Studio running locally for schemas).

## 3. Typography
* **Headings (H1 - H6):** `Fraunces` (Variable Serif). Used for Hero headlines, section titles, card titles. Look for premium, authoritative weight (Bold 700 for Hero, Semi-Bold 600 for standard).
* **Body Text:** `Plus Jakarta Sans` (Sans-Serif). Used for paragraphs, navigation, buttons, metadata.
* **Classes:** Use Tailwind classes `font-serif` for Fraunces and `font-sans` for Plus Jakarta Sans.

## 4. Brand Color Palette
Use these exact custom Tailwind CSS variables mapped in our global stylesheet:

**Global Colors:**
* `bg-kmct-navy` / `text-kmct-navy`: `#0F3A68` (Primary text, footers, trust bars)
* `bg-kmct-light`: `#F8F9FA` (Main website background)
* [cite_start]`bg-teal-600`: (Primary Conversion CTA background - "Apply Now" buttons) [cite: 81]

**Institution-Specific Accent Colors:**
* `kmct-engineering`: `#1E3A8A` (Deep Blue)
* `kmct-business`: `#7F1D1D` (Maroon/Dark Red)
* `kmct-teacher`: `#DC2626` (Bright Red)
* `kmct-training`: `#EC4899` (Pink)
* `kmct-womens`: `#BE185D` (Dark Magenta)
* `kmct-architecture`: `#2563EB` (Medium Blue)
* `kmct-polytechnic`: `#16A34A` (Green)
* `kmct-pharma`: `#3B82F6` (Standard Blue)

## 5. UI/UX Component Guidelines (Manipal/Amity Premium Style)
* **Cards:** Clean white backgrounds (`bg-white`), soft shadows (`shadow-xl`), rounded corners (`rounded-2xl` or `rounded-[2rem]`), subtle border (`border border-gray-100`).
* [cite_start]**Buttons:** * *Primary CTAs (e.g., Apply Now):* Teal background, white text, fully rounded (`rounded-full`)[cite: 81].
  * [cite_start]*Secondary CTAs (e.g., Call Now):* Transparent or white background, navy border (`border-2 border-kmct-navy`), navy text, fully rounded[cite: 81]. [cite_start]Mobile state MUST include a tap-to-call icon[cite: 65, 81].
* **Navigation:** Sticky header. Always visible. [cite_start]Must include "Kallanthode & Pooladikunnu" under/beside the logo to disambiguate from kmct.org[cite: 55, 56, 59, 60, 61].
* **Animations:** * Use the custom `animate-fade-up` class for section reveals (opacity 0 to 1, translate Y up).
  * Stagger children elements on load (e.g., `animation-delay: 200ms`).
  * Hover states on cards/images should zoom slightly (`hover:scale-105 duration-700`).

## 6. Specific Section Rules (From Content Strategy)
When instructed to build a specific section, adhere to these structural rules:
* [cite_start]**Trust Bar:** Full-width navy bar, white text, 5 statistical counters animating on scroll[cite: 83, 84, 85, 86, 87].
* **Decision Section (FAQ):** Named fears, direct answers. Expandable cards. [cite_start]Must sit next to an "Interest Selector" sticky menu on desktop[cite: 99, 100, 103, 123].
* **Fee Transparency:** Must display clear tabular data comparing Govt. Quota vs Total Fees. [cite_start]No hiding numbers[cite: 227, 229, 230, 231].
* **Admissions Step-by-Step:** 4 clear steps. [cite_start]Emphasize "One Call" simplicity[cite: 247, 249, 255].
* **Enquiry Form:** Must include Name, Mobile (WhatsApp preferred), "Looking For" dropdown (required), District dropdown, and Message (optional). [cite_start]Primary CTA: "Send My Enquiry" (teal, full-width)[cite: 343, 344, 345, 346, 356, 359, 360].
## 7. Scroll Animations (The Manipal/Amity Effect)
To create premium scroll transitions, you MUST use the global Intersection Observer setup.
* **Rule:** Do NOT write inline JavaScript or create custom React/Astro scripts for scrolling animations. 
* **Implementation:** Add the class `reveal-on-scroll` to any section, card, or typography block that needs to fade in. 
* **Staggering:** To stagger a grid of cards, add inline styles for delay. Example: `style="transition-delay: 100ms;"`, `style="transition-delay: 200ms;"`, etc.