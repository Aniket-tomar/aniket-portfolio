# Design System Strategy: The Curated Portfolio

## 1. Overview & Creative North Star
The Creative North Star for this design system is **"The Silent Gallery."** 

In a digital world cluttered with loud transitions and heavy borders, this system finds its strength in restraint. It moves beyond the "generic minimalist" look by treating the browser as a physical gallery space. We prioritize intentional asymmetry—where white space is not just "empty," but an active structural element—and a sophisticated hierarchy that allows the portfolio content to breathe. By leaning into tonal shifts rather than hard lines, we create an experience that feels architectural, premium, and deeply professional.

---

### 2. Colors & Surface Philosophy
The palette is a study in cool-toned neutrals and atmospheric depth. We avoid the "flat" look of standard UI by using a sophisticated spectrum of grays that mimic natural light and shadow.

*   **Primary Accent (`#565e74`):** A muted, professional slate. Use this sparingly for moments of high intent—key CTAs or active navigation states.
*   **The "No-Line" Rule:** Standard 1px borders are strictly prohibited for sectioning or layout containment. Contrast is achieved through background shifts. For example, a project gallery section (`surface-container-low`) should sit against the main `surface` (`#f7f9fb`) without a divider line.
*   **Surface Hierarchy & Nesting:** Think of the UI as layers of fine paper. 
    *   **Level 0 (Base):** `surface` (`#f7f9fb`) for the page foundation.
    *   **Level 1 (Sections):** `surface-container-low` (`#f0f4f7`) for large content blocks.
    *   **Level 2 (Objects):** `surface-container-lowest` (`#ffffff`) for cards or high-priority modals to create a "lifted" feel.
*   **The "Glass & Gradient" Rule:** To provide "soul," use a subtle linear gradient on primary CTAs transitioning from `primary` to `primary_container`. For floating navigation bars, use `surface_container_lowest` at 80% opacity with a `24px` backdrop-blur to create a "frosted glass" interaction with the content beneath.

---

### 3. Typography
We use a dual-font strategy to balance editorial character with functional legibility.

*   **The Display Voice (Manrope):** We utilize **Manrope** for all `display` and `headline` roles. Its geometric yet warm construction provides a custom, "high-end boutique" feel. 
    *   *Usage:* Large, airy headlines (`display-lg`) should use generous letter-spacing (-0.02em) to feel tightly curated.
*   **The Functional Voice (Inter):** We use **Inter** for `title`, `body`, and `label` roles. It is the workhorse of the system, ensuring that project descriptions and technical details remain hyper-legible.
*   **Hierarchy as Identity:** Use `headline-lg` (`2rem`) in close proximity to `body-md` (`0.875rem`). This high-contrast scale jump mimics luxury print magazines and avoids the "middle-ground" sizes that make websites look like templates.

---

### 4. Elevation & Depth
In this system, depth is "felt," not "seen." We replace the heavy shadows of the 2010s with **Tonal Layering.**

*   **The Layering Principle:** To highlight a project card, do not add a border. Instead, place a `surface-container-lowest` (`#ffffff`) card on a `surface-container-low` (`#f0f4f7`) background. The 3% shift in luminance is enough for the human eye to perceive a change in elevation.
*   **Ambient Shadows:** If a floating element (like a dropdown) requires a shadow, use a "Cloud Shadow": `Y: 20px, Blur: 40px, Color: rgba(42, 52, 57, 0.05)`. This mimics natural, ambient light.
*   **The "Ghost Border" Fallback:** If a border is required for accessibility (e.g., input fields), use the `outline_variant` token at **15% opacity**. It should be a suggestion of a boundary, not a wall.

---

### 5. Components

#### Buttons
*   **Primary:** Background `primary`, text `on_primary`. Use `lg` (0.5rem) rounded corners. No border.
*   **Secondary:** Background `secondary_container`, text `on_secondary_container`.
*   **Tertiary (The "Editorial" Link):** No background. Text `primary`. Use an animated underline (2px) that grows from the center on hover.

#### Cards & Lists
*   **The Rule of Zero Dividers:** Horizontal lines are forbidden. To separate list items, use increased vertical padding (e.g., `24px` or `32px` from the spacing scale).
*   **Project Cards:** Use `surface_container_lowest`. On hover, transition the background color to `surface_container_high` and apply a subtle `0.5rem` lift via an ambient shadow.

#### Input Fields
*   **Styling:** Use `surface_container_low` as the fill. 
*   **States:** On focus, transition the background to `surface_container_lowest` and apply a "Ghost Border" using the `primary` color at 20% opacity. This creates a "glow" rather than a hard stroke.

#### Navigation (Signature Component)
*   **The Floating Rail:** A bottom-center or top-center floating navigation pill. Use `surface_container_lowest` with a 70% opacity and a `xl` (0.75rem) corner radius. This keeps the portfolio content as the hero of the page.

---

### 6. Do’s and Don’ts

#### Do
*   **Do** use asymmetrical margins. For example, give a header a 15% left margin and a 5% right margin to create a dynamic, editorial feel.
*   **Do** use `body-lg` for introductory paragraphs to establish authority.
*   **Do** ensure all interactive elements have a minimum `44px` touch target, even if the visual element (like a small `label-sm` tag) appears smaller.

#### Don’t
*   **Don't** use 100% black (`#000000`). Use `on_surface` (`#2a3439`) for text to maintain a soft, premium legibility.
*   **Don't** use "standard" drop shadows (e.g., 0px 2px 4px). They feel cheap and "out-of-the-box."
*   **Don't** cram content. If you think there is enough whitespace, add 20% more. Space is the primary indicator of luxury in this system.