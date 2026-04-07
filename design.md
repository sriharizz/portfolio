# Design System Specification: "Portavia" Aesthetic

## 1. Core Philosophy
This UI relies strictly on **massive typography**, **soft glassmorphism**, and **abundant negative space**. It rejects cluttered SaaS layouts in favor of a high-end, editorial tech aesthetic. 
* **Rule 1:** No images or illustrations in the Hero section. 
* **Rule 2:** Do not use standard shadows (`shadow-md`). Use background blurs and subtle glowing borders to create depth.
* **Rule 3:** Absolutely NO red, green, purple, pink, or yellow hues anywhere.

---

## 2. The Dual-State Color System
The UI transitions completely based on the active state. All components must reference these Tailwind equivalents.

### State A: AI Mode (The Raw Terminal)
* **Background:** Pure Black (`bg-[#000000]`)
* **Primary Accent / Active Glows:** Illuminated White (`#FFFFFF`)
* **Primary Text:** Pure White (`text-white`)
* **Secondary Text:** Muted Gray (`text-white/50` or `text-gray-400`)
* **Surface Panels (Cards):** Dark Charcoal (`bg-[#141414]`)

### State B: Data Mode (The Analytical Dashboard)
* **Background:** Deep Graphite (`bg-[#0A0A0A]`)
* **Primary Accent / Active Glows:** Cobalt Blue (`#2563EB`)
* **Primary Text:** Pure White (`text-white`)
* **Secondary Text:** Muted Gray (`text-white/50` or `text-gray-400`)
* **Surface Panels (Cards):** Dark Charcoal (`bg-[#141414]`)

---

## 3. Typography Scale & Tracking
Typography is the primary visual element. It must be perfectly kerned and scaled.
* **Font Family:** A clean, modern sans-serif (e.g., Inter, SF Pro, or default Tailwind Sans).
* **Hero H1 (The Showpiece):** * Size: Viewport relative (`text-[12vw] md:text-[8vw]`)
  * Weight: `font-black`
  * Spacing: `tracking-tighter` (Crucial for the Portavia look)
  * Line Height: `leading-[0.85]` (Tightly stacked lines)
  * Transform: `uppercase`
* **Body Text:**
  * Size: `text-lg md:text-xl`
  * Weight: `font-light`
  * Spacing: `tracking-wide leading-relaxed`
* **Labels / Tags / Buttons:**
  * Size: `text-xs` or `text-[10px]`
  * Weight: `font-bold`
  * Spacing: `tracking-widest uppercase`

---

## 4. Geometry & Glassmorphism
We do not use sharp corners. Everything must feel soft, expensive, and physical.
* **Buttons & Toggle Docks:** `rounded-full`.
* **Bento Grid Cards:** `rounded-3xl`.
* **Glass Effect:** Use `bg-white/10 backdrop-blur-md` for floating elements (nav, docks).
* **Borders:** Subtle definition only. Use `border border-white/10` for floating elements and `border border-white/5` for flat cards.

---

## 5. Animation & Physics (Framer Motion)
Animations must feel weighty and expensive, never linear or bouncy.
* **The Master Easing Curve:** `ease: [0.16, 1, 0.3, 1]` (Use this for all transform and opacity transitions).
* **Hover States (Cards & Buttons):** * `whileHover={{ scale: 1.02 }}`
  * Add a subtle active-color box shadow on hover (e.g., `box-shadow: 0 0 40px rgba(255,255,255,0.1)` for AI Mode, `rgba(37,99,235,0.2)` for Data Mode).
* **Text Reveal:** Fade and slide up (`y: 40` to `y: 0`) over `0.8s`.