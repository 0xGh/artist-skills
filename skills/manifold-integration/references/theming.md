# Styling & Customization Guide

This document explains how to style Manifold Marketplace widgets using CSS variables. It covers the base Manifold theming system, Marketplace-specific overrides, and color scheme utilities.

---

## Overview

Marketplace widgets support light and dark modes by default and automatically follow the end user’s OS color scheme. Styling is done entirely through CSS variables, allowing full customization without modifying component code.

Customization happens at two levels:

1. **Manifold CSS Variables**: global theming used by all widgets
2. **Marketplace CSS Variables**: widget-specific enhancements scoped to `.m-marketplace`

---

## How Styling Works

- Widgets read CSS variables from the DOM
- Variables can be applied globally (`:root`) or scoped to specific widgets
- Light and dark modes are controlled via scheme utility classes
- Marketplace widgets extend the base Manifold theme with additional variables

---

## Manifold CSS Variables

These variables define the core visual system and are shared across all Manifold widgets.

### Theme Colors

Used for actions, status, and emphasis.

- `--manifold-theme--color--primary`
  Primary brand color. Used for main CTAs and links.

- `--manifold-theme--color--secondary`
  Secondary brand color. Used for secondary CTAs and accents.

- `--manifold-theme--color--success`
  Indicates successful actions. Typically green.

- `--manifold-theme--color--error`
  Indicates high-severity issues. Typically red.

- `--manifold-theme--color--warning`
  Indicates medium-severity issues. Typically yellow or orange.

- `--manifold-theme--color--info`
  Indicates low-severity or informational states. Typically blue.

---

### Text

Controls typography, readability, and emphasis.

- `--manifold-text--color--body`
  Default readable text color. Must contrast with page background.

- `--manifold-text--color--muted`
  De-emphasized but actionable text.

- `--manifold-text--color--disabled`
  Non-actionable or disabled text.

- `--manifold-text--color--primary`
  Text color on primary theme backgrounds.

- `--manifold-text--color--secondary`
  Secondary importance text color.

- `--manifold-text--font-family--body`
  Body font family.

- `--manifold-text--font-family-header`
  Header font family.

- `--manifold-text--font-size--body`
  Base body font size.

- `--manifold-text--font-size-header`
  Base header font size.

---

### Borders

Applied to inputs, cards, and interactive elements.

- `--manifold-border--color`
- `--manifold-border--width`
- `--manifold-border--radius`
- `--manifold-border--style`

---

### Surfaces & Backgrounds

- `--manifold-page--color--background`
  Page-level background color.

- `--manifold-element--color--background`
  Background for elevated elements like cards and menus.

---

## Marketplace-Specific CSS Variables

These variables extend the base system and are scoped under `.m-marketplace`.

### Floating Action Buttons (FAB)

- `--m-marketplace-fab--size--primary`
  Primary FAB size. Default: `50px`.

- `--m-marketplace-fab--size--secondary`
  Secondary FAB size. Default: `40px`.

- `--m-marketplace-fab--size--popup`
  FAB size inside popups. Default: `2rem`.

- `--m-marketplace-fab--color--text`
  FAB text color.

- `--m-marketplace-fab--color--background`
  FAB background color.

- `--m-marketplace-fab--color--hover`
  FAB hover background color.

---

### Loading Screens

- `--m-marketplace-loading--color--values`
  Comma-separated HSL values used by loading backgrounds.

- `--m-marketplace-loading--color--background`
  Full-screen loading background color.

- `--m-marketplace-loading--color--overlay`
  Overlay loading color with default alpha of `0.5`.

---

### Popups & Overlays

- `--m-marketplace-popup--color--background`
  Dimmed background behind popups.

- `--m-marketplace-popup--color--button`
  Popup button background color.

- `--m-marketplace-popup--color--button--hover`
  Popup button hover color.

- `--m-marketplace-popup--color--button--text`
  Popup button text color.

- `--m-marketplace-overlay--color--border`
  Border color for overlay layouts.

- `--m-marketplace-bid-overlay--padding`
  Padding for bid overlays.
  Defaults:
  - `80px` for screens wider than `525px`
  - `30px` for screens `≤ 525px`

---

### Inputs

- `--m-marketplace-input--color--background`
  Background color for input fields.

---

## Color Scheme Utilities

Widgets automatically resolve to light or dark mode based on user preferences. You can override this behavior using utility classes.

### Utility Classes

- `.manifold-scheme-light`
- `.manifold-scheme-dark`

These classes:

- Override automatic OS-based theming
- Work by redefining Manifold CSS variables
- Can be applied globally or per widget

### Usage

- Apply to `:root` to affect the entire page
- Apply to an element with `data-widget` to affect only that widget
- Recommended to apply to `html` when using layout widgets like Marketplace or Campaign

---

## Default Schemes

### Light Scheme Defaults

```css
.manifold-scheme-light {
  --manifold-theme--color--primary: hsl(0deg, 0%, 0%);
  --manifold-theme--color--secondary: hsl(0deg, 0%, 95%);
  --manifold-theme--color--success: hsl(120deg, 57%, 53%);
  --manifold-theme--color--error: hsl(0deg, 57%, 53%);
  --manifold-theme--color--warning: hsl(33deg, 65%, 51%);
  --manifold-theme--color--info: hsl(234deg, 82%, 71%);
  --manifold-text--color--primary: hsl(0deg, 0%, 100%);
  --manifold-text--color--secondary: hsl(0deg, 0%, 30%);
  --manifold-text--color--muted: hsla(0deg, 0%, 0%, 0.66);
  --manifold-text--color--disabled: hsla(0deg, 0%, 0%, 0.55);
  --manifold-text--color--body: hsla(0deg, 0%, 0%, 0.87);
  --manifold-border--color: hsl(0deg, 0%, 90%);
  --manifold-page--color--background: hsl(0deg, 0%, 100%);
  --manifold-element--color--background: hsl(0deg, 0%, 100%);
}
```

### Dark Scheme Defaults

```css
.manifold-scheme-dark {
  --manifold-theme--color--primary: hsl(0deg, 0%, 100%);
  --manifold-theme--color--secondary: hsl(0deg, 0%, 10%);
  --manifold-theme--color--success: hsl(120deg, 50%, 32%);
  --manifold-theme--color--error: hsl(0deg, 50%, 32%);
  --manifold-theme--color--warning: hsl(33deg, 52%, 41%);
  --manifold-theme--color--info: hsl(234deg, 36%, 54%);
  --manifold-text--color--primary: hsl(0deg, 0%, 0%);
  --manifold-text--color--secondary: hsl(0deg, 0%, 79%);
  --manifold-text--color--muted: hsla(0deg, 0%, 100%, 0.6);
  --manifold-text--color--disabled: hsla(0deg, 0%, 100%, 0.48);
  --manifold-text--color--body: hsla(0deg, 0%, 100%, 0.87);
  --manifold-border--color: hsl(0deg, 0%, 42%);
  --manifold-page--color--background: hsl(0deg, 0%, 7%);
  --manifold-element--color--background: hsl(0deg, 0%, 20%);
}
```
