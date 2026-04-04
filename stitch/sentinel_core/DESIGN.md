# Design System Document: Tactical Assurance

## 1. Overview & Creative North Star: "The Digital Sentinel"
This design system moves away from the "disposable" feel of gig-economy apps and toward a high-fidelity, editorial experience that commands respect. We call this creative direction **"The Digital Sentinel."**

The objective is to balance the authoritative weight of traditional insurance with the velocity of modern tech. We achieve this through **Organic Brutalism**: using bold, oversized typography and high-contrast color blocks, softened by generous "air" (white space) and rounded geometry. This isn't a flat interface; it is a series of intelligent, stacked layers that feel like physical safety assets.

### Design Principles
*   **Authority Through Scale:** We use dramatic typographic shifts between data and labels to signal what matters most.
*   **Tactile Trust:** Surfaces are not just containers; they are "protective plates." We use tonal layering to create a sense of structural integrity.
*   **Frictionless Velocity:** Interaction targets are oversized for "on-the-move" utility, ensuring the app works as fast as a delivery partner moves.

---

## 2. Colors: Tonal Architecture
We reject the use of generic borders. Trust is built through clarity, not clutter.

### The "No-Line" Rule
**Explicit Instruction:** Do not use 1px solid strokes to separate sections. Boundaries are defined exclusively by shifts in background tokens. For example, a `surface-container-low` card should sit on a `surface` background. The change in tone is the border.

### Primary Palette (The Foundation)
*   **Primary (`#003178`):** Our "Trust Blue." Used for core branding and high-priority actions.
*   **Secondary (`#1b6d24`):** Our "Safety Green." Reserved exclusively for positive financial events (payouts, earnings, active coverage).
*   **Tertiary (`#2b373d`):** Our "Charcoal." Used for secondary navigation or "Heavy" UI elements to ground the experience.

### Surface Hierarchy & Layering
Treat the UI as a series of nested sheets. Use these tokens to create depth:
*   **Surface (`#f8fafb`):** The base canvas.
*   **Surface-Container-Low (`#f2f4f5`):** Secondary content areas or background groupings.
*   **Surface-Container-Highest (`#e1e3e4`):** Use for interactive elements that need to pop against the base.

### The "Glass & Gradient" Rule
To add "soul," apply a subtle linear gradient to Primary CTAs: `primary` to `primary_container`. For floating overlays (e.g., active trip indicators), use **Glassmorphism**: `surface_container_lowest` at 80% opacity with a `24px` backdrop blur.

---

## 3. Typography: Editorial Authority
We pair **Manrope** (Display) with **Inter** (Data) to create an interface that feels like a premium financial journal.

| Level | Token | Font | Size | Character |
| :--- | :--- | :--- | :--- | :--- |
| **Display** | `display-lg` | Manrope | 3.5rem | Bold, tight tracking (-2%). Use for big wins/totals. |
| **Headline** | `headline-md` | Manrope | 1.75rem | Semi-bold. For screen titles and section headers. |
| **Title** | `title-md` | Inter | 1.125rem | Medium. For card titles and primary navigation. |
| **Body** | `body-md` | Inter | 0.875rem | Regular. For policy details and descriptions. |
| **Label** | `label-sm` | Inter | 0.6875rem | All-caps, tracked out (+5%). For metadata. |

---

## 4. Elevation & Depth: Tonal Layering
Traditional shadows create "muddy" UIs. We use **Ambient Depth**.

*   **The Layering Principle:** Instead of a shadow, place a `surface-container-lowest` (#ffffff) card on a `surface` (#f8fafb) background. This creates a "soft lift."
*   **Ambient Shadows:** If an element must float (e.g., a "Start Shift" FAB), use a shadow color tinted with the Primary brand color: `rgba(0, 49, 120, 0.08)` with a `32px` blur and `8px` Y-offset.
*   **The "Ghost Border" Fallback:** If accessibility requires a border, use `outline-variant` at **15% opacity**. It should feel felt, not seen.

---

## 5. Components: Protective Primitives

### Buttons (The "Shield" Action)
*   **Primary:** Solid `primary` fill, `primary-fixed` text. Corner radius: `0.75rem` (md). Minimum height: `56px` for outdoor tap-accuracy.
*   **Secondary:** `surface-container-high` background. No border. For "Manage" or "Edit" actions.

### Cards (The "Policy" Container)
*   **Rule:** Forbid divider lines.
*   **Structure:** Use vertical spacing (24px - 32px) to separate content blocks. Use a `secondary_container` (#a0f399) "pill" in the top right to indicate active coverage status.

### Input Fields (The "Data" Guard)
*   **Style:** Large text (`title-sm`), `surface-container-lowest` background. 
*   **State:** On focus, the background remains, but a 2px `surface_tint` indicator appears at the bottom of the field—never a full-box stroke.

### Specialized Component: The Coverage Pulse
A persistent, glassmorphic header element that uses `secondary` (Safety Green) text to show "Active Protection" status. It uses a `backdrop-blur` of 12px to stay legible over scrolling content.

---

## 6. Do's and Don'ts

### Do
*   **Do** use `display-lg` for the most important number on the screen (e.g., Current Coverage Limit).
*   **Do** use `9999px` (full) roundedness for status chips, but stick to `0.75rem` (md) for functional cards.
*   **Do** ensure high contrast for outdoor use; primary text must never be lighter than `on_surface_variant`.

### Don't
*   **Don't** use 1px dividers. Use a `12px` height block of `surface-container-low` if you must separate sections.
*   **Don't** use pure black for text. Use `on_background` (#191c1d) to maintain a premium, ink-like feel.
*   **Don't** use "Safety Green" for anything other than money or active protection. It is our "Trust Signal."

### Accessibility Note
For delivery partners working in direct sunlight, the contrast between `surface` and `on_surface` must be strictly maintained. Never use a font size smaller than `body-sm` (12px) for critical legal or financial terms.