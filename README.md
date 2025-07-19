# CSS Grid System v1.4

A comprehensive, utility-first CSS Grid system with extensive features and responsive design capabilities. Complete implementation of all planned features from Phase 1-4.

## 🚀 Features

✅ **Complete Feature Set**
- **Phase 1**: Gap control, Auto-sizing, Row utilities, Order control
- **Phase 2**: Alignment, Container sizing, Dense packing  
- **Phase 3**: Template areas, Breakout utilities, Print support
- **Phase 4**: Debug tools, Build integration, Runtime customization

✅ **Responsive Design**
- Mobile-first approach with 5 breakpoints (xs, sm, md, lg, xl)
- All utilities support responsive variants (`sm:`, `md:`, `lg:`, `xl:`)

✅ **Developer Experience**
- Visual debug utilities for development
- Sass/SCSS mixins included
- CSS custom properties for runtime customization
- Comprehensive documentation

## 📋 Quick Start

```html
<!DOCTYPE html>
<html>
<head>
    <link rel="stylesheet" href="CSS.css">
</head>
<body>
    <div class="container">
        <div class="grid gap-md">
            <div class="span-12 md:span-6 lg:span-4">Responsive item 1</div>
            <div class="span-12 md:span-6 lg:span-4">Responsive item 2</div>
            <div class="span-12 md:span-12 lg:span-4">Responsive item 3</div>
        </div>
    </div>
</body>
</html>
```

## 🎯 Key Features

### Gap Control
Control spacing between grid items:
```html
<div class="grid gap-xs">Small gaps</div>
<div class="grid gap-lg">Large gaps</div>
<div class="grid gap-sm md:gap-xl">Responsive gaps</div>
```

### Auto-Sizing Layouts
Create responsive grids that adapt to content:
```html
<div class="grid-auto-fit gap-md">
    <div>Auto-sized item 1</div>
    <div>Auto-sized item 2</div>
    <div>Auto-sized item 3</div>
</div>
```

### Row Spanning
Control vertical layout:
```html
<div class="grid gap-md">
    <div class="span-4 row-span-2">Tall item</div>
    <div class="span-4">Normal item 1</div>
    <div class="span-4">Normal item 2</div>
</div>
```

### Visual Order Control
Reorder items without changing HTML:
```html
<div class="grid gap-md">
    <div class="span-4 order-last">Appears last</div>
    <div class="span-4 order-first">Appears first</div>
    <div class="span-4 order-2">Appears second</div>
</div>
```

### Grid Template Areas
Semantic layouts with named areas:
```html
<div class="grid-layout-sidebar gap-md">
    <div class="area-header">Header</div>
    <div class="area-sidebar">Sidebar</div>
    <div class="area-main">Main Content</div>
    <div class="area-footer">Footer</div>
</div>
```

### Debug Mode
Visual debugging during development:
```html
<body class="debug-breakpoint">
    <div class="grid debug-grid debug-grid-items gap-md">
        <div class="span-6">Debug info visible</div>
        <div class="span-6">Grid columns shown</div>
    </div>
</body>
```

## 📱 Responsive Breakpoints

| Breakpoint | Min Width | Device Target |
|------------|-----------|---------------|
| `xs` (default) | 0px | Mobile phones |
| `sm:` | 480px | Large phones |
| `md:` | 768px | Tablets |
| `lg:` | 1024px | Desktops |
| `xl:` | 1400px | Large screens |

## 🛠️ Sass/SCSS Integration

Use the included mixins for build-time optimization:

```scss
@import 'build-tools';

.my-component {
    @include grid(12, 1rem);
    
    .item {
        @include grid-span(6);
        
        @include breakpoint(md) {
            @include grid-span(4);
        }
    }
}
```

## 🎨 Runtime Customization

Customize using CSS custom properties:

```css
:root {
    --grid-columns: 16;           /* 16-column grid */
    --grid-gap: 2rem;            /* Larger gaps */
    --container-max-width: 1400px; /* Wider container */
}
```

```html
<div class="grid-custom" style="--cols: 5; --gap: 0.5rem;">
    <div>Custom 5-column grid</div>
    <div>Item 2</div>
    <div>Item 3</div>
    <div>Item 4</div>
    <div>Item 5</div>
</div>
```

## 📊 All Available Utilities

<details>
<summary>📏 <strong>Column Spanning</strong></summary>

```css
.span-1 through .span-12  /* Column spanning */
.span-auto                /* Auto-sized columns */
```
</details>

<details>
<summary>📍 <strong>Positioning</strong></summary>

```css
.start-1 through .start-12  /* Column start position */
.start-auto                 /* Auto positioning */
.row-start-1 through .row-start-6  /* Row start position */
.row-span-1 through .row-span-6    /* Row spanning */
```
</details>

<details>
<summary>📐 <strong>Gap Control</strong></summary>

```css
.gap-0, .gap-xs, .gap-sm, .gap-md, .gap-lg, .gap-xl, .gap-2xl
.gap-x-{size}  /* Column gap only */
.gap-y-{size}  /* Row gap only */
```
</details>

<details>
<summary>🔄 <strong>Order Control</strong></summary>

```css
.order-1 through .order-12  /* Numeric order */
.order-first                /* Order: -1 */
.order-last                 /* Order: 999 */
.order-none                 /* Order: 0 */
```
</details>

<details>
<summary>📐 <strong>Alignment</strong></summary>

```css
/* Individual item alignment */
.justify-start, .justify-center, .justify-end, .justify-stretch
.items-start, .items-center, .items-end, .items-stretch

/* Container alignment */
.grid-justify-start, .grid-justify-center, .grid-items-center
```
</details>

<details>
<summary>📦 <strong>Container Sizing</strong></summary>

```css
.container        /* Default (1200px) */
.container-sm     /* 640px */
.container-md     /* 768px */
.container-lg     /* 1024px */
.container-xl     /* 1280px */
.container-2xl    /* 1536px */
.container-full   /* No max-width */
```
</details>

<details>
<summary>🏗️ <strong>Layout Types</strong></summary>

```css
.grid              /* Standard 12-column grid */
.grid-auto-fit     /* Auto-fit layout */
.grid-auto-fill    /* Auto-fill layout */
.grid-dense        /* Dense packing */
.grid-custom       /* Runtime customizable */
```
</details>

<details>
<summary>🎭 <strong>Template Areas</strong></summary>

```css
.grid-layout-sidebar     /* Sidebar layout */
.grid-layout-three-col   /* Three-column layout */
.grid-layout-holy-grail  /* Holy grail layout */

.area-header, .area-sidebar, .area-main, .area-footer, .area-nav, .area-aside
```
</details>

<details>
<summary>🌊 <strong>Breakout Utilities</strong></summary>

```css
.full-width      /* Break out to viewport edges */
.breakout-wide   /* Break out with controlled margins */
```
</details>

<details>
<summary>🖨️ <strong>Print Support</strong></summary>

```css
.print:span-12, .print:span-6, .print:span-4, .print:span-3
.print:hidden, .print:block, .print:inline, .print:grid
```
</details>

<details>
<summary>🐛 <strong>Debug Utilities</strong></summary>

```css
.debug-grid         /* Show grid column visualization */
.debug-grid-items   /* Show item boundaries and classes */
.debug-breakpoint   /* Show current breakpoint indicator */
```
</details>

## 🌐 Browser Support

- **CSS Grid**: All modern browsers (95%+ support)
- **CSS Custom Properties**: All modern browsers
- **Subgrid**: Firefox 71+, Safari 16+, Chrome/Edge (future)

## 📁 File Structure

```
css-grid-system/
├── CSS.css              # Main CSS file with all utilities
├── index.html           # Comprehensive demo page
├── build-tools.scss     # Sass/SCSS mixins for build integration
├── GRID_DOCS.md         # Complete documentation
├── FEATURE_WORKPLAN.md  # Implementation roadmap
└── README.md            # This file
```

## 📚 Documentation

- **[Complete Documentation](GRID_DOCS.md)** - Comprehensive guide with examples
- **[Feature Workplan](FEATURE_WORKPLAN.md)** - Implementation roadmap and status
- **[Live Demo](index.html)** - Interactive examples of all features

## 🎯 Use Cases

- **Landing Pages**: Hero sections, feature grids, testimonials
- **Dashboards**: Card layouts, data visualization, responsive panels  
- **Blogs**: Article layouts, sidebars, comment sections
- **E-commerce**: Product grids, checkout flows, category pages
- **Documentation**: Multi-column layouts, code examples, navigation

## 🚀 Getting Started

1. **Download or link to `CSS.css`**
2. **Add to your HTML**: `<link rel="stylesheet" href="CSS.css">`
3. **Start building**: Use `container` → `grid` → `span-*` classes
4. **Add responsive behavior**: Use `md:span-*`, `lg:span-*` variants
5. **Enable debug mode**: Add `debug-breakpoint` to `<body>` during development

## 💡 Pro Tips

- Start with mobile-first design (`span-12 md:span-6 lg:span-4`)
- Use gap utilities instead of margins for spacing
- Leverage `grid-auto-fit` for responsive card layouts
- Use debug utilities during development
- Consider print styles with `print:` utilities

## 📄 License

MIT License - See [LICENSE](LICENSE) file for details.

---

**🎉 Complete implementation of all Phase 1-4 features!**

*Built with modern CSS Grid, designed for performance, accessibility, and developer experience.*