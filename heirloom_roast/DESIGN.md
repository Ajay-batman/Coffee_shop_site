# Design System Strategy: The Artisanal Lens

## 1. Overview & Creative North Star
**Creative North Star: "The Curated Hearth"**

This design system moves away from the sterile, rigid grids of traditional e-commerce to embrace a high-end editorial feel that mirrors the tactile experience of a premium coffee house. We are not building a "website"; we are designing a digital window into a physical space. 

The aesthetic is driven by **Organic Asymmetry**. Rather than perfectly centered blocks, we utilize offset imagery and overlapping typography to create a sense of movement and "human" imperfection. High-quality photography—steam rising from a ceramic mug, the texture of burlap, the soft smile of a barista—is the protagonist. The UI is the quiet, sophisticated stage that supports it. By utilizing depth through tonal layering rather than borders, the interface feels like natural materials stacked upon one another.

---

## 2. Colors & Surface Philosophy

The palette is a sophisticated interplay of earth and cream, designed to evoke the warmth of a freshly poured latte and the freshness of the bean's origin.

### The Palette
*   **Primary (`#361f1a`)**: A deep, roasted espresso. Use this for high-impact text and primary actions.
*   **Secondary (`#5c614a`)**: A muted moss green. This represents the organic, "rustic" element of the brand.
*   **Background/Surface (`#fbfbe2`)**: A warm, creamy beige that prevents the "digital fatigue" of pure white.

### The "No-Line" Rule
**Explicit Instruction:** 1px solid borders are strictly prohibited for sectioning or containment. To separate a "Menu Highlights" section from a "Story" section, transition from `surface` to `surface-container-low`. Boundaries are felt through color shifts, never seen through lines.

### Surface Hierarchy & Nesting
Treat the UI as a physical desk. 
*   **Base Layer:** `surface` (#fbfbe2).
*   **In-Page Sections:** Use `surface-container-low` (#f5f5dc) for large content blocks.
*   **Interactive Cards:** Use `surface-container-lowest` (#ffffff) to provide a "bright" lift that draws the eye.
*   **Nesting:** A `surface-container-high` (#eaead1) element should only exist within a `surface-container` or `surface-variant` parent to indicate a deeper level of focus.

### The "Glass & Gradient" Rule
To add a "signature" polish, use semi-transparent overlays for navigation and floating elements.
*   **Glassmorphism:** Apply `surface_variant` at 80% opacity with a `backdrop-filter: blur(12px)`. This allows the warmth of the background photography to "bleed" into the UI.
*   **Signature Gradients:** Use a subtle linear gradient from `primary` (#361f1a) to `primary_container` (#4e342e) for hero buttons to give them a three-dimensional, "steamed" quality.

---

## 3. Typography: Editorial Authority

We use a high-contrast pairing to balance heritage (Serif) with modern efficiency (Sans-Serif).

*   **Display & Headlines (Noto Serif):** This is our "Rustic" voice. Use `display-lg` for hero statements. Increase letter-spacing slightly for a more premium, relaxed feel.
*   **Body & UI (Manrope):** This is our "Modern" voice. It provides clarity in the shop's menu, hours, and functional text. 
*   **The Hierarchy Strategy:** Headlines should always be in `primary` or `on_surface`. Labels and captions in `secondary` add a botanical, soft touch to the metadata.

---

## 4. Elevation & Depth

Depth is achieved through **Tonal Layering** and ambient light, not heavy drop shadows.

*   **The Layering Principle:** Instead of a shadow, place a `surface-container-lowest` card on a `surface-dim` background. The change in "paper weight" creates the perceived lift.
*   **Ambient Shadows:** For floating elements like a "Cart" modal, use a shadow color derived from `on_surface` at 5% opacity with a 32px blur. It should look like a soft glow of light blocked by an object, not a digital effect.
*   **The "Ghost Border" Fallback:** If a container requires definition against a similar background, use `outline_variant` at 15% opacity. It should be barely perceptible.

---

## 5. Components

### Buttons
*   **Primary:** Background: `primary` (#361f1a) | Text: `on_primary`. Roundedness: `md` (0.375rem).
*   **Secondary:** Background: `secondary_container` | Text: `on_secondary_container`. No border.
*   **Tertiary:** Text-only in `primary` with a `surface-variant` underline that expands on hover.

### Cards (The "Editorial" Block)
*   **Rule:** Forbid divider lines.
*   **Style:** Use `surface-container-low` background with `lg` (0.5rem) corner radius. 
*   **Imagery:** Images within cards should have a slight "overhang" or be inset by the `3` spacing token (1rem) to create a framed, gallery effect.

### Input Fields
*   **Style:** Background `surface_container_highest`. No border. 
*   **Active State:** The bottom edge receives a 2px `primary` accent. Avoid the "box" look; favor the "underline" look to maintain a clean, modern aesthetic.

### Signature Component: The "Bean Origin" Chip
*   **Context:** For characterizing coffee types.
*   **Style:** Use `secondary_fixed` background with `on_secondary_fixed` text. Use `full` roundedness to create a pebble-like organic shape.

---

## 6. Do's and Don'ts

### Do
*   **Do** use asymmetrical margins. If a text block is on the left, let the image on the right bleed off the edge of the screen.
*   **Do** use the `20` (7rem) and `24` (8.5rem) spacing tokens for top/bottom padding of sections to allow the design to "breathe."
*   **Do** use `notoSerif` for numbers in menus (prices) to make them feel like a vintage chalkboard.

### Don't
*   **Don't** use 100% black. Use `primary` (#361f1a) for the darkest elements to keep the "warmth."
*   **Don't** use "standard" 1px dividers. Use a 4rem vertical gap or a subtle change in background color.
*   **Don't** use sharp 0px corners. Even the most "modern" element needs at least the `sm` (0.125rem) radius to feel approachable and "soft."