# Intern Application Dashboard

A dashboard page with navigation, cards, a table and a form, built with HTML and modern CSS.
Task 9 of my Bloomrix internship. No JavaScript is used.

## Files
- index.html - the page
- style.css - all the styling
- images/profile.jpg - photo in the header

## Token System & Architecture
All colors, spacing, font sizes, font weights, line heights, radii, shadows, gradients, and layout dimensions are custom properties declared in `:root`.

## Theming Logic
- **Automatic System Preference:** `prefers-color-scheme: dark` automatically maps to the dark token palette without overriding default light mode behavior.
- **Manual Toggle Override:** Manual themes use attribute selector rules (`html[data-theme="dark"]` / `#theme-toggle:checked`) to override OS preferences without breaking automatic system mode detection.

## Native CSS Nesting
Native CSS nesting is used across component sub-layers (`& > main`, `& h2`, `&::after`).

## Cascade Layers
Order declared: `@layer reset, base, components, utilities, overrides;`
- `reset`: `box-sizing` and margin resets via `:where()`.
- `base`: Variable tokens, themes, typography, and focus ring settings.
- `components`: Divided into named sub-layers (`layout`, `header`, `widgets`, `table`, `form`).
- `utilities`: Helper classes (`.text-center`, `.text-muted`).
- `overrides`: Top-priority accessibility overrides (`prefers-reduced-motion`, `prefers-contrast`).

## Container Queries
Stat-card wrappers (`.widget`) configure `container-type: inline-size`. Card typography scales dynamically with `cqi` units.

## DevTools Testing Evidence
- **Viewport Testing:** Verified in Chrome DevTools at `375px` (mobile stack), `768px` (tablet flex), and `1280px` (desktop sticky side-panel).
- **Theme & Accessibility:** Simulated `prefers-color-scheme: dark` and `prefers-reduced-motion: reduce` in the Rendering tab.

## How to Run
Open index.html with Live Server in Visual Studio Code, or in any web browser.