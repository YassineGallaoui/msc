# Minimal SCSS

A lightweight collection of SCSS utilities for modern web development. This library provides essential utility classes for grid systems, flexbox layouts, typography, spacing, and more.

## Features

- 🎨 **Modern Grid System** - CSS Grid-based system with 4/8/12 columns across breakpoints
- 🔧 **Flexbox Utilities** - Complete flexbox property classes with responsive variants  
- 📝 **Typography System** - Scalable font sizes from 2xs to 6xl
- 📏 **Spacing Utilities** - Comprehensive margin, padding, and position classes (0-160px)
- 🎯 **Router Utilities** - Page transition animations for SPA routing
- 📊 **Stats Components** - Debug overlay for displaying screen stats and FPS
- 🌙 **Dark Mode Support** - Built-in dark mode color scheme support
- 📱 **Responsive Design** - Mobile-first approach with 5 breakpoint system
- 🎨 **CSS Custom Properties** - Modern theming with CSS variables

## Installation

```bash
npm install minimal-scss
```

## Usage

### Import the complete library

```scss
@use "minimal-scss/scss/common";
```

### Import individual modules

```scss
@use "minimal-scss/scss/utils/variables";
@use "minimal-scss/scss/utils/base";
@use "minimal-scss/scss/utils/grid";
@use "minimal-scss/scss/utils/flex";
@use "minimal-scss/scss/utils/text";
@use "minimal-scss/scss/utils/spacing";
@use "minimal-scss/scss/utils/router";
@use "minimal-scss/scss/utils/stats";
```

## Breakpoints

The library uses a mobile-first responsive approach with the following breakpoints:

| Breakpoint | Size     | Usage           |
|------------|----------|-----------------|
| `sm`       | ≥577px   | Small tablets   |
| `md`       | ≥769px   | Tablets         |
| `lg`       | ≥993px   | Small desktops  |
| `xl`       | ≥1201px  | Large desktops  |
| `xxl`      | ≥1441px  | Extra large     |

## Grid System

### Container

```html
<div class="container">
  <!-- Your content here -->
</div>
```

### Grid Classes

```html
<div class="row">
  <div class="col-12 sm-col-4 md-col-6 lg-col-4">Column</div>
  <div class="col-12 sm-col-4 md-col-2 lg-col-8">Column</div>
</div>
```

### Grid System Details

The grid system uses CSS Grid with different column counts per breakpoint:
- **Default (mobile)**: 4 columns
- **sm and up**: 8 columns  
- **md and up**: 12 columns

### Offset Classes

```html
<div class="row">
  <div class="col-6 offset-3">Centered column with offset</div>
  <div class="col-4 lg-offset-2">Column with responsive offset</div>
</div>
```

### Sub-grid

```html
<div class="col-6 sub-grid">
  <div class="col-3">Nested grid item</div>
  <div class="col-3">Nested grid item</div>
</div>
```

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

Available sizes: `3xs`, `2xs`, `xs`, `sm`, `md`, `lg`, `xl`, `2xl`, `3xl`, `4xl`, `5xl`, `6xl`

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
$grid-columns-lg: 16;

@use "minimal-scss/scss/common";
```

### Available Variables

```scss
// Typography
$font-family-base: -apple-system, Roboto, "Helvetica Neue", Arial, sans-serif;
$font-size-base: 16px;
$line-height-base: 1.5;

// Spacing
$spacing-unit: 8px;
$container-padding: 15px;

// Grid
$grid-columns-sm: 4;
$grid-columns-md: 8;
$grid-columns-lg: 12;
```

## Additional Components

### Router Utilities

For single-page applications with custom routing:

```html
<div class="page-container" id="current-content">
  <!-- Current page content -->
</div>
<div class="page-container" id="new-content">
  <!-- New page content -->
</div>
```

CSS classes for page transitions:
- `.page-container` - Base container for pages
- `.page-exit` - Applied when page is leaving (fade out + slide up)
- `.page-enter` - Applied when page is entering (fade in + slide down)

### Stats Component

Development overlay for displaying screen information:

```html
<div class="stats show">
  <!-- Stats content populated by JavaScript -->
</div>
```

- `.stats` - Hidden by default
- `.stats.show` - Visible overlay positioned top-right
- Designed to work with a JavaScript stats system

### Base Styles

The library includes a CSS reset and base styles:
- Box-sizing border-box reset
- Smooth scrolling
- Responsive body layout with flexbox
- Image max-width 100%
- List styling with consistent spacing

## Browser Support

Due to modern CSS features used in this library, browser support is limited to:

- **Chrome 117+** (August 2023)
- **Firefox 113+** (May 2023)  
- **Safari 16.2+** (December 2022)
- **Edge 117+** (September 2023)

### Modern CSS Features Used

- **CSS Subgrid** (sub-grid classes)
- **Dynamic Viewport Units** (`100dvh`, `100dvw`)
- **CSS `color-mix()` function** (grid overlay)
- **`backdrop-filter`** (stats component)

### Graceful Degradation

Most utility classes will work in older browsers, but some advanced features may not function:
- Grid overlay visualization requires `color-mix()` support
- Sub-grid classes fall back to regular grid
- Dynamic viewport units fall back to regular viewport units
- Stats component backdrop blur won't work without `backdrop-filter`

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## License

ISC

## Author

Yassine Gallaoui

## Repository

[GitHub Repository](https://github.com/YassineGallaoui/minimal-scss)