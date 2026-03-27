# Design System: The Kinetic Archive

## 1. Overview & Creative North Star
**Creative North Star: "The Digital Artifact"**

This design system moves away from the static, "flat" dashboard web patterns of the last decade. Instead, it treats student biodata as a living, breathing holographic record. We are building a high-end, sci-fi interface that feels like a terminal from a near-future research vessel.

To break the "template" look, we utilize **Intentional Asymmetry**. Layouts should not be perfectly mirrored; use the `20` (5rem) and `24` (6rem) spacing tokens to create breathing room that feels editorial and curated. Elements should overlap—a holographic ID card might bleed over the edge of a section container, breaking the "box-in-box" monotony. We rely on high-contrast typography scales where `display-lg` headings sit alongside `label-sm` technical metadata to create a sense of sophisticated complexity.

---

## 2. Colors & Surface Philosophy
The palette is rooted in deep space blacks and high-energy luminescent cyans.

*   **Primary (`#6dddff`):** Used for critical data points and active states. 
*   **Secondary/Tertiary (`#03c1fb` / `#82a3ff`):** These provide tonal depth to data visualizations, preventing the UI from feeling monochromatic.
*   **Neutral Surfaces:** We use a spectrum from `surface-container-lowest` (#000000) to `surface-bright` (#2c2b33) to define hierarchy.

### The "No-Line" Rule
Standard 1px borders are strictly prohibited for sectioning. Definition must be achieved through **background color shifts**. A profile summary (`surface-container-low`) should sit atop the main page (`background`) without a stroke. Separation is felt through tonal change, not drawn with a line.

### The Glass & Gradient Rule
To achieve the "Holographic" feel, all primary cards must use **Glassmorphism**.
*   **Background:** `surface-container` at 40-60% opacity.
*   **Backdrop Blur:** 12px to 20px.
*   **The Signature Glow:** Instead of a border, use a linear gradient stroke (from `primary` to `transparent`) at 15% opacity to "catch the light" on the top-left edge only.

### Signature Textures
Apply a subtle noise texture (2% opacity) over the `background` to eliminate banding in gradients. Use a gradient transition from `primary` to `secondary` for high-impact elements like skill progress bars or "Download Resume" CTAs.

---

## 3. Typography
We pair the aggressive, geometric 'Orbitron' (mapped to `spaceGrotesk` tokens for technical implementation) with the Swiss-precision of 'Inter'.

*   **Display & Headlines (`Orbitron`):** These are your "HUD" (Heads-Up Display) elements. Use `display-lg` for names and `headline-sm` for section headers. The wide tracking of Orbitron conveys a high-tech, cinematic feel.
*   **Title & Body (`Inter`):** 'Inter' handles the heavy lifting of legibility. Use `title-md` for labels and `body-md` for bio descriptions. 
*   **The Metadata Aesthetic:** Use `label-sm` in all-caps with 0.1rem letter spacing for secondary technical data (e.g., "TIMESTAMP: 2023.08.12" or "UID: 8829-X").

---

## 4. Elevation & Depth
In a sci-fi UI, depth is not simulated by "shadows" from an invisible sun, but by **Tonal Layering** and **Luminescence**.

*   **The Layering Principle:** Stack `surface-container-lowest` elements on top of `surface-container-high` sections to create "recessed" bays. Conversely, use `surface-bright` for floating modals to create "projection."
*   **Ambient Shadows:** Traditional black shadows are forbidden. If an element "floats," use a diffuse glow using the `primary` color at 5-8% opacity. This mimics light being cast from a holographic screen onto the backplate.
*   **Ghost Borders:** For accessibility on interactive inputs, use the `outline-variant` token at 20% opacity. It should look like a faint laser-etched guide, not a solid box.

---

## 5. Components

### Holographic Cards
*   **Structure:** No dividers. Use `Spacing 6` (1.5rem) to separate the profile image from the text content.
*   **Header:** The student’s name in `headline-lg` (`Orbitron`) with a 2px `primary` underline that only extends 40px wide.

### Kinetic Skill Bars
*   **Track:** `surface-container-highest`.
*   **Fill:** A linear gradient from `primary` to `tertiary`. 
*   **Animation:** Use an easing function (`cubic-bezier(0.22, 1, 0.36, 1)`) to make the bar fill "snap" into place on page load.

### Interactive Buttons
*   **Primary:** Solid `primary` background with `on-primary` text. No rounded corners (`rounded-none` or `rounded-sm`).
*   **Secondary:** Ghost style. `outline` color at 30% opacity, shifting to 100% opacity with a `primary-dim` outer glow on hover.

### Input Fields
*   **Style:** Underline only (2px `outline-variant`). When focused, the line morphs into `primary` and a faint `primary-container` glow fills the background (10% opacity).

### Chips & Tags
*   **Selection:** Use `label-md`. Background `secondary-container`, text `on-secondary-container`. Shape should be `rounded-sm` to maintain the techy edge.

---

## 6. Do's and Don'ts

### Do:
*   **Do** use asymmetrical margins. If the left content is flush, let the right content float or stagger.
*   **Do** use "Data Scaffolding." Add small, non-functional tech labels (e.g., "SYS_VER 4.0") in `label-sm` to corners of cards to enhance the sci-fi immersion.
*   **Do** leverage the Light Mode toggle by swapping `background` for `surface-bright` and ensuring the `primary` cyan remains legible against the light backdrop by using `primary-dim`.

### Don't:
*   **Don't** use 100% opaque borders. They kill the "light-based" holographic aesthetic.
*   **Don't** use standard "Drop Shadows." They feel organic and earthy; this system is synthetic and digital. Use glows or tonal shifts instead.
*   **Don't** use rounded corners above `0.5rem` (lg). Excessive roundness makes the UI feel "friendly" and "consumer-grade" rather than "high-end developer-grade." Keep it sharp.