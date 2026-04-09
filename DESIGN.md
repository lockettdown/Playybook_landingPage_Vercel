# Design System Strategy: The Elite Playbook

## 1. Overview & Creative North Star
Basketball is a game of explosive movement contained within a rigid geometry. This design system seeks to replicate that tension through a creative north star we call **"The Kinetic Court."**

Unlike generic sports apps that rely on heavy borders and bright, distracting gradients, this system utilizes a high-end editorial approach. We favor sophisticated, layered surfaces that feel like a premium coaching tablet. We break the "template" look by using intentional asymmetry in our grid, high-contrast typography scales that demand attention, and an atmospheric dark theme that makes the court-inspired accents (Electric Blue and Court Orange) feel like glowing light sources in a darkened arena.

## 2. Colors
Our palette is rooted in the "Deep Charcoal" of the arena after the lights go down, punctuated by high-frequency accents that guide the eye to critical coaching actions.

### Brand Palette
*   **Background (Surface):** `#131313` – Our absolute base. 
*   **Primary (Electric Blue):** `#a2c9ff` – Used for navigation, active states, and primary information headers.
*   **Secondary (Court Orange):** `#ffb5a0` – Our "Action" color. Reserved for high-priority CTAs, scoring, and critical alerts.
*   **Tertiary (Strategy Gold):** `#ffb954` – Used for highlight states and secondary performance metrics.

### The "No-Line" Rule
To maintain a premium, seamless feel, **1px solid borders are prohibited for sectioning.** We do not "box" our content. Boundaries must be defined solely through background color shifts. For example, a card utilizing `surface-container-highest` (`#353534`) should sit directly on a `surface` (`#131313`) background. The contrast is the container.

### The Glass & Gradient Rule
To move beyond a flat UI, utilize "Atmospheric Depth." Floating elements (like navigation bars or modal overlays) must use **Glassmorphism**. Apply a semi-transparent `surface-variant` with a `backdrop-blur` of 20px. 
*   **Signature Texture:** For primary CTAs, use a subtle linear gradient from `primary` (`#a2c9ff`) to `primary-container` (`#3394f1`) at a 135-degree angle to provide a "lit from within" professional polish.

## 3. Typography
Our typography is an exercise in authoritative hierarchy. It bridges the gap between a high-end fashion magazine and a high-performance sports car dashboard.

*   **Headlines (Plus Jakarta Sans):** Bold, modern, and aggressive. Use `display-lg` (3.5rem) for hero moments and `headline-md` (1.75rem) for section titles. The tight letter-spacing and heavy weight convey the "Track. Coach. Dominate." mindset.
*   **Body & Labels (Inter):** Chosen for its exceptional legibility on dark backgrounds. Use `body-md` (0.875rem) for primary data points.
*   **Visual Logic:** The extreme scale difference between our `display-lg` headlines and `label-sm` metadata creates a sense of "Editorial Intent," making the app feel curated rather than just a database of stats.

## 4. Elevation & Depth
Depth in this system is achieved through **Tonal Layering**, not structural lines. We treat the screen as a series of physical layers.

*   **The Layering Principle:** Stack your containers. A `surface-container-low` section should house `surface-container-highest` cards. This creates a soft, natural lift.
*   **Ambient Shadows:** If a card must "float" (e.g., a draggable play on the Whiteboard), use a shadow with a 32px blur at 6% opacity. The shadow color should be a tinted version of the `on-surface` color (`#e5e2e1`), never a flat black.
*   **The "Ghost Border" Fallback:** If accessibility requirements demand a stroke, use the `outline-variant` token at **15% opacity**. This creates a "suggestion" of a border that doesn't break the fluid aesthetic.

## 5. Components

### Buttons
*   **Primary:** Court Orange (`secondary`) background with `on-secondary` (`#5f1500`) text. Use `xl` (1.5rem) rounded corners.
*   **Tertiary (Ghost):** No background. `primary` text. Use a `ghost-border` (15% opacity outline) only on hover.

### Cards & Lists
*   **Rule:** **Forbid the use of divider lines.** 
*   Separate list items using `spacing-4` (1rem) of vertical white space or by alternating between `surface-container-low` and `surface-container-high`.
*   **Corner Radius:** All cards must use `lg` (1rem) or `xl` (1.5rem) rounding to soften the aggressive typography.

### Chips (Player Stats/Tags)
*   **Style:** Pill-shaped (`full` roundedness). Use `surface-container-highest` as the base with `label-md` typography.

### Input Fields
*   **State:** Use `surface-container-lowest` (`#0e0e0e`) for the input well to create an "inset" feel. When focused, use a `primary` glow (2px outer shadow) rather than a heavy border.

### Contextual Tooltips
*   **Style:** Glassmorphic. `surface-bright` at 80% opacity with a heavy backdrop blur. This ensures they "pop" against the dark background without feeling heavy.

## 6. Do's and Don'ts

### Do
*   **Do** use asymmetrical layouts. For example, allow a "Recent Games" card to bleed off the right edge of the screen to encourage horizontal scrolling.
*   **Do** use the `spacing-12` and `spacing-16` tokens to give elements room to breathe. High-end design is defined by the space you *don't* use.
*   **Do** use high-contrast text. Ensure `on-surface` (`#e5e2e1`) is used for all primary reading to maintain AAA accessibility against the dark backgrounds.

### Don't
*   **Don't** use 100% opaque white. It causes "halation" (glowing effect) on dark screens which strains the eyes. Use our `on-surface` token.
*   **Don't** use standard "Material Design" shadows. Our shadows are ambient and tinted.
*   **Don't** cram information. If a screen feels busy, increase the background-tier contrast and the spacing scale rather than adding borders.