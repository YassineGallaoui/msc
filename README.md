# Minimal Styling Classes (MSCCSS)

A lightweight collection of SCSS/css utility classes for modern web development. Bootstrap or Tailwind, but lighter. This library provides essential utility classes for flexbox, typography, spacing, and base styles.  
This is not meant to have everything you need, each SCSS/css rule was added only after answering the question: "will I use this intensively?". If the answer is no, then you will not find that styling rule in this library.

## Features

- 🔧 **Flexbox Utilities** - Complete flexbox property classes with responsive variants  
- 📝 **Typography System** - Scalable font sizes from 2xs to 6xl, plus fluid `clamp()`-based display sizes
- 📏 **Spacing Utilities** - Comprehensive margin, padding, and position classes (0-160px)
- 🌙 **Dark Mode Support** - Built-in dark mode color scheme support
- 📱 **Responsive Design** - Mobile-first approach with 5 breakpoint system
- 🎨 **CSS Custom Properties** - Modern theming with CSS variables

## Related Projects

For additional functionality that was previously part of this library:

- **[Vanilla JS Helpers](https://github.com/YassineGallaoui/vanilla-js-helpers)** - Grid system, stats overlay, and client-side router for vanilla JavaScript projects
- **[Next FE Helpers](https://github.com/YassineGallaoui/next-fe-helpers)** - Grid system and stats overlay components for Next.js projects

## Installation

```bash
npm install msccss
```

## Usage

### Import pre-built CSS in JavaScript

The easiest way to use msc is to import the pre-built CSS file in your main and shared JavaScript file:

```javascript
// Import in your main JS file (e.g., main.js, app.js, common.js)
import '/node_modules/msccss/dist/main.min.css';
```

This approach:
- ✅ **Simple**: No build configuration needed
- ✅ **Global**: All utility classes work everywhere in your HTML
- ✅ **Performance**: Uses optimized, pre-built CSS
- ✅ **No conflicts**: Avoids SCSS compilation issues
- ✅ **Bundle integration**: Works with Vite, Webpack, Parcel, etc.


## Breakpoints

The library uses a mobile-first responsive approach with the following breakpoints:

| Breakpoint | Size     | Usage           |
|------------|----------|-----------------|
| `sm`       | >576px   | Small tablets   |
| `md`       | >768px   | Tablets         |
| `lg`       | >992px   | Small desktops  |
| `xl`       | >1200px  | Large desktops  |
| `xxl`      | >1440px  | Extra large     |

## Flexbox Utilities

### Display

```html
<div class="flex">Flexbox container</div>
<div class="md-flex">Flexbox on medium screens and up</div>
```

### Direction

```html
<div class="flex row">Row direction</div>
<div class="flex column">Column direction</div>
<div class="flex md-row">Responsive direction</div>
```

Available directions: `row`, `row-reverse`, `column`, `column-reverse`

### Wrap

```html
<div class="flex wrap">Flex wrap</div>
<div class="flex nowrap">No wrap</div>
<div class="flex wrap-reverse">Wrap reverse</div>
```

### Justify Content

```html
<div class="flex jc-center">Center content</div>
<div class="flex jc-between">Space between</div>
<div class="flex jc-around">Space around</div>
```

Available options: `jc-start`, `jc-center`, `jc-end`, `jc-between`, `jc-around`, `jc-evenly`

### Align Items

```html
<div class="flex ai-center">Center items vertically</div>
<div class="flex ai-start">Align to start</div>
<div class="flex ai-stretch">Stretch items</div>
```

Available options: `ai-start`, `ai-center`, `ai-end`, `ai-stretch`, `ai-baseline`

### Align Content

```html
<div class="flex ac-center">Center content</div>
<div class="flex ac-between">Space between content</div>
```

Available options: `ac-start`, `ac-center`, `ac-end`, `ac-stretch`, `ac-between`, `ac-around`

### Gap

```html
<div class="flex gap-2">Gap on both axes</div>
<div class="flex gap-x-3">Horizontal gap only</div>
<div class="flex gap-y-1">Vertical gap only</div>
```

## Typography

### Font Sizes

```html
<p class="fs-sm">Small text</p>
<p class="fs-md">Medium text (default)</p>
<p class="fs-lg">Large text</p>
<p class="fs-xl md-fs-2xl">Responsive text size</p>
```

Available sizes: `2xs`, `xs`, `sm`, `md`, `lg`, `xl`, `2xl`, `3xl`, `4xl`, `5xl`, `6xl`

### Fluid Font Sizes

For hero and display headings, the fixed `fs-*` scale can feel too rigid. The `fs-fluid-*` classes scale smoothly with the viewport using `clamp()`, interpolating linearly between a minimum and maximum size:

```html
<h1 class="fs-fluid-2xl">Hero heading that scales with the viewport</h1>
<h2 class="fs-fluid-lg">Section heading</h2>
```

Available sizes and their min → max ranges (in `rem`, relative to `--font-size-base`):

| Class           | Min      | Max      |
|-----------------|----------|----------|
| `fs-fluid-sm`   | 1.25rem  | 1.5rem   |
| `fs-fluid-md`   | 1.5rem   | 2.25rem  |
| `fs-fluid-lg`   | 2rem     | 3rem     |
| `fs-fluid-xl`   | 2.5rem   | 4rem     |
| `fs-fluid-2xl`  | 3rem     | 5rem     |

The size grows linearly between two viewport widths and clamps outside that range. The interpolation breakpoints are exposed as CSS custom properties so you can override them at runtime without recompiling:

```css
:root {
  --fs-fluid-min-vw: 20; /* default: 320px @ 16px base — size sits at min below this */
  --fs-fluid-max-vw: 96; /* default: 1536px @ 16px base — size sits at max above this */
}

/* e.g. reach the max size earlier, at a 1280px viewport */
.hero {
  --fs-fluid-max-vw: 80;
}
```

## Spacing

### Margin and Padding

```html
<div class="m-2">Margin on all sides</div>
<div class="mt-3 mb-3">Margin top and bottom</div>
<div class="p-4">Padding on all sides</div>
<div class="px-2 py-4">Horizontal and vertical padding</div>
```

### Available Spacing Values

The spacing system uses an 8px base unit with the following scale:

| Class | Value | Pixels |
|-------|-------|--------|
| `0` | 0 | 0px |
| `025` | 0.25 × 8px | 2px |
| `050` | 0.5 × 8px | 4px |
| `075` | 0.75 × 8px | 6px |
| `1` | 1 × 8px | 8px |
| `2` | 2 × 8px | 16px |
| `3` | 3 × 8px | 24px |
| `4` | 4 × 8px | 32px |
| `5` | 5 × 8px | 40px |
| `6-20` | 6-20 × 8px | 48px-160px |

### Position Utilities

```html
<div class="t-2">Top: 16px</div>
<div class="r-4 b-4">Right and bottom: 32px</div>
<div class="inset-0">Full coverage</div>
```

Available position classes: `t-*`, `r-*`, `b-*`, `l-*`, `inset-*`

## Color Scheme

### CSS Custom Properties

The library provides CSS custom properties for consistent theming:

```css
:root {
  /* Theme Colors */
  --background-color: #ebecd6;
  --foreground-color: #0a100d;
  --accent-light-color: #7ba9f4;
  --accent-color: #3066be;
  --accent-dark-color: #0e4193;
  
  /* Status Colors */
  --success-color: #28a745;
  --danger-color: #dc3545;
  --warning-color: #ffc107;
  --info-color: #17a2b8;
  
  /* Animation */
  --transition-duration: 0.3s;
}
```

### Dark Mode

Colors automatically adapt to dark mode when `prefers-color-scheme: dark` is detected.

## Customization

### Override Variables

You can customize the library by overriding SCSS variables:

```scss
// Override before importing
$breakpoint-md: 800px;
$spacing-unit: 10px;

@use "msccss/scss/main";
```

### Available Variables

```scss
// Typography
$font-family-base: -apple-system, Roboto, "Helvetica Neue", Arial, sans-serif;
$font-size-base: 16px;
$line-height-base: 1.5;

// Spacing
$spacing-unit: 8px;
```

## Base Styles

The library includes a CSS reset and base styles:
- Box-sizing border-box reset
- Smooth scrolling
- Responsive body layout with flexbox

## Browser Support

The library uses CSS custom properties and modern flexbox features that are well-supported across modern browsers.

## License

ISC

## Author

Yassine Gallaoui