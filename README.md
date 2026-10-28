# Intern Application Dashboard

A dashboard page with navigation, cards, a table and a form, built with HTML and modern CSS.
Task 9 of my Bloomrix internship. No JavaScript is used.

## Files
- index.html - the page
- style.css - all the styling
- images/profile.jpg - photo in the header

## Variable System
All colors, spacing, font sizes, font weights, line heights, radii, shadows and layout breakpoints are custom properties declared in `:root`. Components consume `var()` tokens cleanly.

## Themes
- **Light theme:** Default tokens declared in `:root`.
- **Dark theme:** Toggled automatically via `prefers-color-scheme: dark` or manually using `:root:has(#theme-toggle:checked)`.
- **Symmetric Control:** Unchecking `#theme-toggle` on a dark-preference OS enforces Light mode (`:root:has(#theme-toggle:not(:checked))`).

## Native CSS Nesting
Native CSS nesting (`& > main`, `& h2`, `&::after`) is used directly in component rules. Supported across all major modern browsers (Chrome 112+, Firefox 117+, Safari 16.5+).

## Cascade Layers
Declared in exact order: `@layer reset, base, components, utilities, overrides;`
- `reset`: `box-sizing` and margin resets via `:where()`.
- `base`: Variable tokens, themes, typography, and focus ring settings.
- `components`: Divided into named sub-layers (`layout`, `header`, `widgets`, `table`, `form`).
- `utilities`: Small helper utility classes (`.text-center`, `.text-muted`).
- `overrides`: Top-priority accessibility overrides (`prefers-reduced-motion`, `prefers-contrast`).

## Container Queries
Stat-card wrappers (`.widget`) configure `container-type: inline-size`. Card typography uses `cqi` units and adapts into a multi-column flex layout when crossing 16rem width.

## DevTools Testing Evidence
- **Viewport Testing:** Tested in Chrome DevTools at `375px` (mobile stack), `768px` (tablet flex), and `1280px` (desktop sticky side-panel).
- **Theme & Motion Testing:** Simulated `prefers-color-scheme: dark` and `prefers-reduced-motion: reduce` in the DevTools Rendering panel to verify zero-animation rules and high-contrast color token swaps.

## How to Run
Open index.html with Live Server in Visual Studio Code, or in any web browser.