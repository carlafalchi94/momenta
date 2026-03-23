# Design System Specification

## 1. Overview & Creative North Star: "The Nocturnal Monolith"

This design system is a rejection of the "Default Digital" aesthetic. It is built for 'momenta'—an experience centered on inward reflection, daily return, and the quiet gravity of self-connection. Our North Star is **"The Nocturnal Monolith"**: a digital environment that feels like an architect-designed private library at midnight. 

We achieve high-end editorial status by moving away from standard grids and bright UI patterns. Instead, we use **intentional asymmetry**, **cinematic scale**, and **tonal depth**. The UI does not compete for attention; it waits to be discovered. By utilizing ultra-thin borders and monochromatic layering, we create a space that feels rare, private, and emotionally intelligent.

---

## 2. Color & Atmosphere

The palette is strictly monochromatic and nocturnal. It favors the shadows, using light only to guide the eye to the most critical points of interaction.

### The Palette (Material Mapping)
- **Background (`#080808`):** The absolute base. Used for the deep "void" of the application.
- **Surface (`#111111`):** Primary container level. 
- **Secondary Surface (`#1a1a1a`):** For nested elements or elevated interaction states.
- **Primary Text (`#f0ebe3`):** A warm, bone-white that provides high contrast without the clinical harshness of pure white.
- **Muted Text (`#7a7470`):** For secondary information and supporting labels.
- **Accent (`#9a948e`):** Used for subtle emphasis or active states.
- **CTA White (`#faf6f0`):** Reserved exclusively for the most critical actions.

### The "No-Line" Rule
Standard 1px borders are strictly prohibited for sectioning. Differentiation must be achieved through:
1.  **Background Shifts:** Transitioning from `surface` to `surface-container-low`.
2.  **Negative Space:** Using the `Spacing Scale (16, 20, 24)` to create distinct zones.
3.  **Tonal Stacking:** Placing a `surface-container-highest` element against a `surface-dim` background.

### The Glass & Gradient Rule
To prevent a "flat" look, use glassmorphism for floating panels (Modals, Navigation Bars). Use a `12px - 20px` backdrop blur with a semi-transparent `surface` fill. 
*Note: Gradients are only permitted as subtle vertical fades (e.g., `surface` to `background`) to ground the bottom of a screen.*

---

## 3. Typography: The Editorial Voice

Hierarchy is the primary tool for navigation. We use a "High-Low" pairing: an evocative serif for expression and a technical mono for utility.

- **Display & Headlines (Instrument Serif Regular):** Used for "Inward" moments. Headlines should be large, often asymmetrical in placement, and never italicized. This is the "soul" of the brand.
- **Labels, Inputs, & CTAs (DM Mono):** Used for "Action" moments. The monospaced nature provides a sense of luxury-tech precision and deliberate input.

| Level | Token | Font | Size | Case |
| :--- | :--- | :--- | :--- | :--- |
| **Display** | `display-lg` | Instrument Serif | 3.5rem | Sentence |
| **Headline** | `headline-md` | Instrument Serif | 1.75rem | Sentence |
| **Action** | `label-md` | DM Mono | 0.75rem | Uppercase |
| **Metadata** | `label-sm` | DM Mono | 0.68rem | Sentence |
| **Body** | `body-md` | Inter* | 0.875rem | Sentence |

*\*Inter is used sparingly for long-form reading; DM Mono remains the primary functional typeface.*

---

## 4. Elevation & Depth: Tonal Layering

In this system, depth is not "up" (shadows), but "in" (tonal shifts). 

- **The Layering Principle:** Treat the screen as stacked sheets of matte paper. To "lift" an object, use `surface-container-high` (`#2a2a2a`) against the `background` (`#080808`).
- **Ambient Shadows:** Shadows should be nearly invisible. Use a 40px blur, 0px offset, at 6% opacity using a tinted `#000000` to create a "haze" rather than a drop shadow.
- **The Ghost Border:** If a boundary is required for accessibility, use a **0.5pt** line in `outline-variant` (`#474747`) at 20% opacity. It should feel like a hairline fracture, not a container.
- **Background Orbs:** Large, neutral-gray orbs (low opacity, no glow) should be placed partially off-screen. They serve as "structural anchors" to break the symmetry of the layout.

---

## 5. Components

### Buttons & CTAs
- **Primary:** Background: `CTA White (#faf6f0)`, Text: `DM Mono (#1c1c18)`. Rectangular (0px radius).
- **Secondary:** Border: `Ghost Border (0.5px)`, Text: `DM Mono (#f0ebe3)`.
- **Tertiary/Ghost:** Text: `DM Mono (#7a7470)`, no background. 1px underline on hover.

### Input Fields
- **Styling:** Underline-only (0.5px) using `Borders (#272727)`. No bounding boxes.
- **Label:** `DM Mono`, small, placed above the input.
- **Focus State:** Border transitions to `Primary Text (#f0ebe3)`.

### Cards & Lists
- **Rule:** No divider lines. 
- **Structure:** Use vertical spacing (e.g., `spacing-10`) to separate list items. For cards, use a slight background shift to `surface-container-low` with 0px corner radius.

### The "Momenta" Orb (Background Asset)
- **Execution:** CSS or SVG radial gradients. No "blur" filters that cause performance lag; use smooth dithered gradients. Position them asymmetrically (e.g., top-right at 15% visibility) to create a cinematic, un-centered balance.

---

## 6. Do’s and Don’ts

### Do
- **Do** embrace extreme white space. Let the nocturnal palette breathe.
- **Do** align text to a strict baseline grid but vary the horizontal margins for an editorial feel.
- **Do** use 0px border-radii for everything. Sharp corners imply precision and architectural intent.
- **Do** use `DM Mono` for all numerical data.

### Don’t
- **Don’t** use italics. They feel too "soft" for this system.
- **Don’t** use rounded corners. It breaks the "Luxury-Tech" aesthetic.
- **Don’t** use colorful icons. All iconography must be stroke-based (0.75px weight) in `Primary Text` or `Muted Text`.
- **Don’t** center-align everything. Use left-heavy layouts with "floating" elements to create tension.

---

## 7. Spacing Scale

Our spacing is generous and deliberate, intended to slow the user down.

- **Micro (0.5 - 2):** For internal component padding (e.g., button labels).
- **Macro (8 - 24):** For layout margins and section spacing.
- **Key Value:** `spacing-16 (5.5rem)` is the standard "breath" between major content blocks.