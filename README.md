# Intern Application Dashboard

A dashboard page with navigation, cards, a table and a form, built with HTML and modern CSS.
Task 9 of my Bloomrix internship. No JavaScript is used.

## Files
- index.html - the page
- style.css - all the styling
- images/profile.jpg - photo in the header

## Variable system
All colors, spacing, font sizes, radii, shadows and layout sizes are custom properties in :root.
Components only use var(), so a theme only needs new values for the same names.

## Themes
- Light theme: the default values in :root.
- Dark theme: the same variable names with new values. It is used when the system prefers dark
  (prefers-color-scheme), and when the Dark theme checkbox in the header is ticked.
  The checkbox works without JavaScript because :root:has(#theme-toggle:checked) is matched
  when the box is checked.
- If the system is already in dark mode, the page is dark even when the box is unchecked.

## Cascade layers
@layer reset, base, components, utilities, overrides;
- reset: box-sizing and margin removal using :where()
- base: variables, themes, typography, links, focus
- components: layout, header, cards, table, form
- utilities: .text-center and .text-muted
- overrides: reduced motion and more contrast
A later layer always beats an earlier one, so no !important is needed.

## Functions
- calc(): sticky offsets and the slanted bottom edge of the welcome panel
- min(): the page width
- max(): the header padding
- clamp(): headings and the numbers in the stat cards
- repeat(), minmax(), fit-content(): the grids and the side panel

## Selectors
- :where() in the reset, :is() in the form and focus styles, :not() in the facts lists
- :has() for the theme switch, the required stars, the form states and the pending table rows

## Container query
Each stat-card sits inside a .widget with container-type: inline-size. When the widget is 16rem
wide or more, the card changes its layout. The big number uses the cqi unit. At desktop width the
cards stack, because each widget is narrow there. At tablet width they are wider, so the number
sits beside the note. The layout follows the container, not the window.

## Animations
- The progress bar grows with @keyframes when the page loads.
- The dot in front of Pending pulses and pauses on hover.
- Reduced motion turns every animation and transition off.

## Other features
- @supports: the glass card uses backdrop-filter only if the browser supports it.
- Counter: the application steps are numbered with counter-reset and counter-increment.
- Columns: the About text uses column-count, column-width, column-gap, column-rule, column-span
  and break-inside.
- Logical properties: inline-size, margin-inline, padding-block, inset-inline-end and
  border-inline-start are used in the components.

## Tested
Mobile 375px, tablet 768px and desktop 1280px. Dark theme and reduced motion were tested with
the DevTools Rendering panel.

## How to run
Open index.html with Live Server in Visual Studio Code, or in any web browser.