# CSS Grid System Documentation

A comprehensive, utility-first CSS Grid system with extensive features and responsive design capabilities.

## 🚀 Features Overview

✅ **Core Grid System**
- 12-column responsive grid
- Mobile-first design approach
- CSS custom properties for easy customization

✅ **Phase 1: Essential Utilities**
- Gap control utilities (xs, sm, md, lg, xl, 2xl)
- Auto-sizing layouts (auto-fit, auto-fill)
- Row spanning and positioning
- Visual order control

✅ **Phase 2: Layout & Alignment**
- Grid item alignment utilities
- Container responsive sizing
- Dense grid packing
- Grid flow control

✅ **Phase 3: Advanced Features**
- Subgrid support (future-ready)
- Grid template areas
- Full-width breakout utilities
- Print layout support

✅ **Phase 4: Developer Experience**
- Enhanced CSS custom property API
- Debug and development utilities
- Runtime customization
- Breakpoint indicators

## 📋 Quick Reference

### Basic Grid Structure

```html
<div class="container">
  <div class="grid gap-md">
    <div class="span-6">Half width</div>
    <div class="span-6">Half width</div>
  </div>
</div>
```

### Responsive Example

```html
<div class="grid gap-sm md:gap-lg">
  <div class="span-12 md:span-6 lg:span-4">Responsive item</div>
  <div class="span-12 md:span-6 lg:span-4">Responsive item</div>
  <div class="span-12 md:span-12 lg:span-4">Responsive item</div>
</div>
```

## 🎯 Phase 1: Essential Utilities

### Gap Control Utilities

Control spacing between grid items:

```css
.gap-0     /* 0 */
.gap-xs    /* 0.25rem */
.gap-sm    /* 0.5rem */
.gap-md    /* 1rem */
.gap-lg    /* 1.5rem */
.gap-xl    /* 2rem */
.gap-2xl   /* 3rem */
```

**Directional Gap Control:**
```css
.gap-x-md  /* Column gap only */
.gap-y-lg  /* Row gap only */
```

**Usage Examples:**
```html
<div class="grid gap-xs">...</div>
<div class="grid gap-sm md:gap-lg">...</div>
<div class="grid gap-x-md gap-y-sm">...</div>
```

### Auto-Sizing Utilities

Create responsive layouts that adapt to content:

```css
.span-auto        /* Auto-sized column */
.grid-auto-fit    /* Auto-fit layout */
.grid-auto-fill   /* Auto-fill layout */
```

**Usage Examples:**
```html
<!-- Auto-fit: Items expand to fill space -->
<div class="grid-auto-fit gap-md">
  <div>Item 1</div>
  <div>Item 2</div>
  <div>Item 3</div>
</div>

<!-- Mixed auto and fixed sizing -->
<div class="grid gap-md">
  <div class="span-auto">Flexible</div>
  <div class="span-6">Fixed 6 columns</div>
  <div class="span-auto">Flexible</div>
</div>
```

### Row Spanning Utilities

Control vertical space:

```css
.row-span-1     /* Span 1 row */
.row-span-2     /* Span 2 rows */
.row-span-3     /* Span 3 rows */
.row-span-4     /* Span 4 rows */
.row-span-auto  /* Auto row span */
```

**Row Positioning:**
```css
.row-start-1    /* Start at row 1 */
.row-start-2    /* Start at row 2 */
.row-end-3      /* End at row 3 */
```

**Usage Examples:**
```html
<div class="grid gap-md">
  <div class="span-4 row-span-2">Tall item</div>
  <div class="span-4">Normal item</div>
  <div class="span-4">Normal item</div>
  <div class="span-8">Wide item below</div>
</div>
```

### Order Control Utilities

Reorder items visually without changing HTML:

```css
.order-1       /* Order: 1 */
.order-2       /* Order: 2 */
.order-first   /* Order: -1 (first) */
.order-last    /* Order: 999 (last) */
.order-none    /* Order: 0 (source order) */
```

**Usage Examples:**
```html
<div class="grid gap-md">
  <div class="span-3 order-last">Appears last</div>
  <div class="span-3 order-first">Appears first</div>
  <div class="span-3 order-2">Appears third</div>
  <div class="span-3 order-1">Appears second</div>
</div>
```

## 🎨 Phase 2: Layout & Alignment

### Grid Item Alignment

Align items within their grid areas:

**Individual Item Alignment:**
```css
.justify-start    /* justify-self: start */
.justify-center   /* justify-self: center */
.justify-end      /* justify-self: end */
.justify-stretch  /* justify-self: stretch */

.items-start      /* align-self: start */
.items-center     /* align-self: center */
.items-end        /* align-self: end */
.items-stretch    /* align-self: stretch */
```

**Grid Container Alignment:**
```css
.grid-justify-start    /* justify-items: start */
.grid-justify-center   /* justify-items: center */
.grid-items-start      /* align-items: start */
.grid-items-center     /* align-items: center */
```

**Usage Examples:**
```html
<div class="grid gap-md grid-items-center" style="min-height: 200px;">
  <div class="span-4 justify-start">Left aligned</div>
  <div class="span-4 justify-center">Center aligned</div>
  <div class="span-4 justify-end">Right aligned</div>
</div>
```

### Container Responsive Sizing

Different container sizes for different use cases:

```css
.container-sm    /* max-width: 640px */
.container-md    /* max-width: 768px */
.container-lg    /* max-width: 1024px */
.container-xl    /* max-width: 1280px */
.container-2xl   /* max-width: 1536px */
.container-full  /* max-width: none */
```

**Usage Examples:**
```html
<div class="container-sm">
  <div class="grid gap-md">
    <div class="span-12">Narrow container content</div>
  </div>
</div>

<div class="container-lg">
  <div class="grid gap-md">
    <div class="span-12">Wide container content</div>
  </div>
</div>
```

### Dense Grid Packing

Automatically fill empty grid spaces:

```css
.grid-dense      /* grid-auto-flow: dense */
.grid-row-dense  /* grid-auto-flow: row dense */
.grid-col-dense  /* grid-auto-flow: column dense */
.grid-flow-row   /* grid-auto-flow: row */
.grid-flow-col   /* grid-auto-flow: column */
```

**Usage Examples:**
```html
<div class="grid grid-dense gap-md">
  <div class="span-6">Large item</div>
  <div class="span-3">Small item</div>
  <div class="span-2">Tiny item</div>
  <div class="span-4">Medium item - fills gaps</div>
</div>
```

## 🔮 Phase 3: Advanced Features

### Grid Template Areas

Semantic layouts with named areas:

**Predefined Layouts:**
```css
.grid-layout-sidebar     /* Header, sidebar, main, footer */
.grid-layout-three-col   /* Three-column layout */
.grid-layout-holy-grail  /* Classic holy grail layout */
```

**Named Areas:**
```css
.area-header    /* grid-area: header */
.area-sidebar   /* grid-area: sidebar */
.area-main      /* grid-area: main */
.area-footer    /* grid-area: footer */
.area-nav       /* grid-area: nav */
.area-aside     /* grid-area: aside */
```

**Usage Examples:**
```html
<div class="grid-layout-sidebar gap-md">
  <div class="area-header">Site Header</div>
  <div class="area-sidebar">Navigation</div>
  <div class="area-main">Main Content</div>
  <div class="area-footer">Site Footer</div>
</div>
```

### Full-Width Breakout Utilities

Break out of container constraints:

```css
.full-width     /* Break out to viewport edges */
.breakout-wide  /* Break out with margins */
```

**Usage Examples:**
```html
<div class="container">
  <div class="grid gap-md">
    <div class="span-12">Regular content</div>
    <div class="full-width">Full viewport width</div>
    <div class="span-12">Back to container</div>
  </div>
</div>
```

### Subgrid Support

Future-ready subgrid utilities:

```css
.subgrid-cols   /* grid-template-columns: subgrid */
.subgrid-rows   /* grid-template-rows: subgrid */
.subgrid-both   /* Both columns and rows */
```

### Print Layout Support

Special utilities for print media:

```css
.print\:span-12   /* Full width when printing */
.print\:span-6    /* Half width when printing */
.print\:hidden    /* Hidden when printing */
.print\:block     /* Block display when printing */
```

## 🛠️ Phase 4: Developer Experience

### Enhanced CSS Custom Properties

```css
:root {
  --grid-gap: 1rem;
  --grid-gap-x: var(--grid-gap);
  --grid-gap-y: var(--grid-gap);
  --grid-columns: 12;
  --container-padding: var(--grid-gap);
  --container-max-width: 1200px;
  --min-col-width: 250px;
}
```

### Runtime Customization

Dynamic layouts using CSS variables:

```css
.grid-custom      /* Uses --cols and --gap variables */
.grid-custom-auto /* Uses --min-width and --gap variables */
```

**Usage Examples:**
```html
<div class="grid-custom" style="--cols: 5; --gap: 0.5rem;">
  <div>Item 1</div>
  <div>Item 2</div>
  <div>Item 3</div>
  <div>Item 4</div>
  <div>Item 5</div>
</div>
```

### Debug Utilities

Visual debugging tools for development:

```css
.debug-grid        /* Shows grid column visualization */
.debug-grid-items  /* Shows item boundaries and classes */
.debug-breakpoint  /* Shows current breakpoint */
```

**Usage Examples:**
```html
<!-- Add to body for breakpoint indicator -->
<body class="debug-breakpoint">

<!-- Add to grid for column visualization -->
<div class="grid debug-grid debug-grid-items gap-md">
  <div class="span-4">Debug mode active</div>
  <div class="span-8">Shows grid and class info</div>
</div>
```

## 📱 Responsive Design

All utilities support responsive variants:

### Breakpoints

```css
/* Default (0px+) */
.gap-md

/* Small (480px+) */
.sm\:gap-lg

/* Medium (768px+) */
.md\:gap-xl

/* Large (1024px+) */
.lg\:gap-2xl

/* Extra Large (1400px+) */
.xl\:gap-sm
```

### Responsive Examples

**Responsive Grid:**
```html
<div class="grid gap-sm md:gap-lg">
  <div class="span-12 md:span-6 lg:span-4">
    Full width on mobile, half on tablet, third on desktop
  </div>
  <div class="span-12 md:span-6 lg:span-4">
    Responsive item 2
  </div>
  <div class="span-12 md:span-12 lg:span-4">
    Full width on mobile and tablet, third on desktop
  </div>
</div>
```

**Responsive Order:**
```html
<div class="grid gap-md">
  <div class="span-12 order-last md:order-first">
    Last on mobile, first on tablet+
  </div>
  <div class="span-12 order-first md:order-last">
    First on mobile, last on tablet+
  </div>
</div>
```

**Responsive Alignment:**
```html
<div class="grid gap-md items-start md:items-center lg:items-end">
  <div class="span-6 justify-start md:justify-center">
    Responsive alignment
  </div>
</div>
```

## 🎯 Common Patterns

### Card Grid

```html
<div class="grid-auto-fit gap-md">
  <div class="demo-card">Card 1</div>
  <div class="demo-card">Card 2</div>
  <div class="demo-card">Card 3</div>
</div>
```

### Hero Section

```html
<div class="grid gap-lg items-center" style="min-height: 60vh;">
  <div class="span-12 md:span-8 md:start-3 justify-center items-center">
    <h1>Hero Title</h1>
    <p>Hero description</p>
  </div>
</div>
```

### Magazine Layout

```html
<div class="grid grid-dense gap-md">
  <div class="span-8 row-span-2">Featured article</div>
  <div class="span-4">Side article 1</div>
  <div class="span-4">Side article 2</div>
  <div class="span-6">Regular article</div>
  <div class="span-6">Regular article</div>
</div>
```

### Sidebar Layout

```html
<div class="grid-layout-sidebar gap-md">
  <header class="area-header">Site Header</header>
  <nav class="area-sidebar">Navigation</nav>
  <main class="area-main">Main Content</main>
  <footer class="area-footer">Site Footer</footer>
</div>
```

## 🔧 Customization

### CSS Custom Properties

You can customize the grid system by overriding CSS custom properties:

```css
:root {
  --grid-columns: 16;     /* 16-column grid instead of 12 */
  --grid-gap: 2rem;       /* Larger default gap */
  --container-max-width: 1400px; /* Wider container */
  --min-col-width: 300px; /* Wider auto-fit columns */
}
```

### Creating Custom Utilities

Add your own utilities following the same patterns:

```css
/* Custom gap sizes */
.gap-xs { gap: 0.125rem; }
.gap-3xl { gap: 4rem; }

/* Custom spans */
.span-16 { grid-column-end: span 16; }

/* Custom containers */
.container-custom { 
  max-width: 1600px; 
  margin: 0 auto; 
  padding: 0 var(--container-padding); 
}
```

## 🌐 Browser Support

- **CSS Grid**: All modern browsers (IE 11+ with `-ms-` prefixes)
- **CSS Custom Properties**: All modern browsers (IE 11+ needs fallbacks)
- **Subgrid**: Firefox 71+, Safari 16+, Chrome/Edge (coming soon)

### Progressive Enhancement

The grid system is designed to work gracefully in older browsers:

```css
/* Fallback for older browsers */
.grid-item {
  width: 100%;  /* Full width fallback */
}

@supports (display: grid) {
  .grid {
    display: grid;
    /* Grid-specific styles */
  }
}
```

## 📊 Performance

- **CSS Size**: ~15KB minified (~3KB gzipped)
- **Runtime Performance**: Excellent (native CSS Grid)
- **Memory Usage**: Minimal (utility classes only)

## 🚀 Getting Started

1. **Include the CSS:**
   ```html
   <link rel="stylesheet" href="CSS.css">
   ```

2. **Create a basic grid:**
   ```html
   <div class="container">
     <div class="grid gap-md">
       <div class="span-6">Column 1</div>
       <div class="span-6">Column 2</div>
     </div>
   </div>
   ```

3. **Add responsive behavior:**
   ```html
   <div class="grid gap-sm md:gap-lg">
     <div class="span-12 md:span-6">Responsive column</div>
   </div>
   ```

4. **Use debug mode during development:**
   ```html
   <body class="debug-breakpoint">
     <div class="grid debug-grid debug-grid-items">
       <!-- Your grid content -->
     </div>
   </body>
   ```

## 💡 Tips and Best Practices

1. **Start with mobile-first design**
2. **Use gap utilities instead of margins**
3. **Leverage auto-sizing for flexible layouts**
4. **Use debug utilities during development**
5. **Test with different content lengths**
6. **Consider print styles for documents**

## 📚 Additional Resources

- [CSS Grid Complete Guide](https://css-tricks.com/snippets/css/complete-guide-grid/)
- [Grid by Example](https://gridbyexample.com/)
- [MDN CSS Grid Layout](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Grid_Layout)

---

**Version**: 1.4 (Complete Implementation)  
**Last Updated**: 2024  
**Status**: All Phase 1-4 features implemented ✅ 