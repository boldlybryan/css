# CSS Grid System Documentation

A modern, framework-agnostic CSS grid system built with CSS Grid and responsive design principles.

## 📖 Table of Contents

- [Quick Start](#quick-start)
- [Core Concepts](#core-concepts)
- [Grid Container](#grid-container)
- [Column Spanning](#column-spanning)
- [Column Positioning](#column-positioning)
- [Responsive Design](#responsive-design)
- [Technical Implementation](#technical-implementation)
- [Examples](#examples)
- [Browser Support](#browser-support)

## 🚀 Quick Start

```html
<!DOCTYPE html>
<html>
<head>
    <link rel="stylesheet" href="CSS.css">
</head>
<body>
    <div class="container">
        <div class="grid">
            <div class="span-6">Half width</div>
            <div class="span-6">Half width</div>
        </div>
    </div>
</body>
</html>
```

## 🎯 Core Concepts

### **12-Column Grid System**
- Based on a 12-column grid layout
- Columns are equal width using CSS Grid `1fr` units
- Uses CSS custom properties for configuration

### **Mobile-First Responsive**
- Base classes apply to all screen sizes
- Responsive prefixes override at larger breakpoints
- Progressive enhancement approach

### **Semantic Class Names**
- `span-*` - Controls how many columns an element spans
- `start-*` - Controls which column an element starts at
- `{breakpoint}:` - Responsive prefix for larger screens

## 🏗️ Grid Container

### `.container`
Centers content with max-width and responsive padding.

```css
.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 1rem; /* var(--grid-gap) */
}
```

### `.grid`
Creates a 12-column CSS Grid layout.

```css
.grid {
  display: grid;
  grid-template-columns: repeat(12, 1fr);
  gap: 1rem; /* var(--grid-gap) */
  margin: 1rem 0; /* var(--grid-gap) */
}
```

**CSS Custom Properties:**
- `--grid-gap: 1rem` - Space between grid items
- `--grid-columns: 12` - Number of columns (12 by default)

## 📏 Column Spanning

### Basic Span Classes
Controls how many columns an element spans across.

| Class | Width | Use Case |
|-------|-------|----------|
| `span-1` | 8.33% | Small elements, icons |
| `span-2` | 16.67% | Narrow sidebars |
| `span-3` | 25% | Quarter width |
| `span-4` | 33.33% | Third width |
| `span-5` | 41.67% | Custom layouts |
| `span-6` | 50% | Half width |
| `span-7` | 58.33% | Custom layouts |
| `span-8` | 66.67% | Two-thirds width |
| `span-9` | 75% | Three-quarters width |
| `span-10` | 83.33% | Wide content |
| `span-11` | 91.67% | Almost full |
| `span-12` | 100% | Full width |

### Examples

```html
<!-- Equal thirds -->
<div class="grid">
    <div class="span-4">Column 1</div>
    <div class="span-4">Column 2</div>
    <div class="span-4">Column 3</div>
</div>

<!-- Sidebar + main content -->
<div class="grid">
    <div class="span-3">Sidebar</div>
    <div class="span-9">Main content</div>
</div>

<!-- Half and half -->
<div class="grid">
    <div class="span-6">Left half</div>
    <div class="span-6">Right half</div>
</div>
```

## 🎯 Column Positioning

### Start Position Classes
Controls which column an element starts at (1-12).

| Class | Starts At | Use Case |
|-------|-----------|----------|
| `start-1` | Column 1 | Default position |
| `start-2` | Column 2 | Skip first column |
| `start-3` | Column 3 | Skip two columns |
| `start-4` | Column 4 | Center 6-col content |
| `start-auto` | Auto | Reset positioning |

### Positioning Examples

```html
<!-- Centered 6-column content -->
<div class="grid">
    <div class="span-6 start-4">
        Centered content (cols 4-9)
    </div>
</div>

<!-- Two columns with gap -->
<div class="grid">
    <div class="span-4 start-1">Left (cols 1-4)</div>
    <div class="span-4 start-8">Right (cols 8-11)</div>
    <!-- Columns 5-7 remain empty = gap -->
</div>

<!-- Offset content -->
<div class="grid">
    <div class="span-8 start-3">
        8 columns starting at column 3
    </div>
</div>
```

## 📱 Responsive Design

### Breakpoints

| Prefix | Min Width | Device |
|--------|-----------|--------|
| (none) | 0px | Mobile (base) |
| `sm:` | 480px | Small tablets |
| `md:` | 768px | Tablets |
| `lg:` | 1024px | Desktops |
| `xl:` | 1400px | Large screens |

### Responsive Examples

```html
<!-- Mobile-first responsive columns -->
<div class="grid">
    <div class="span-12 md:span-6 lg:span-4">
        <!-- 1 column mobile, 2 columns tablet, 3 columns desktop -->
    </div>
    <div class="span-12 md:span-6 lg:span-4">Item 2</div>
    <div class="span-12 md:span-6 lg:span-4">Item 3</div>
</div>

<!-- Responsive positioning -->
<div class="grid">
    <div class="span-12 md:span-8 md:start-3 lg:span-6 lg:start-4">
        <!-- Mobile: full width -->
        <!-- Tablet: 8 cols starting at col 3 -->
        <!-- Desktop: 6 cols starting at col 4 -->
    </div>
</div>

<!-- Reset positioning -->
<div class="grid">
    <div class="span-6 start-7 lg:start-auto">
        <!-- Positioned on smaller screens, auto on desktop -->
    </div>
</div>
```

## ⚙️ Technical Implementation

### CSS Properties Used

**Span Classes:**
```css
.span-6 {
  grid-column-end: span 6; /* Uses longhand for compatibility */
}
```

**Start Position Classes:**
```css
.start-4 {
  grid-column-start: 4;
}
```

### Why Longhand Properties?

We use `grid-column-end: span X` instead of `grid-column: span X` to avoid conflicts when combining span and start classes:

```html
<!-- This works reliably -->
<div class="span-6 start-4">
  <!-- grid-column-start: 4; grid-column-end: span 6; -->
</div>
```

If we used `grid-column: span 6`, it could override the `grid-column-start: 4` depending on source order.

### CSS Cascade and Specificity

- All grid classes have the same specificity `(0,0,1,0)`
- Responsive variants are ordered from smallest to largest breakpoint
- Later breakpoints override earlier ones due to source order
- Mobile-first approach means base classes apply to all screen sizes

## 📋 Complete Examples

### **Hero + Sidebar Layout**

```html
<div class="container">
    <div class="grid">
        <!-- Hero section -->
        <div class="span-12 lg:span-8">
            <h1>Hero Content</h1>
            <p>Main content area</p>
        </div>
        
        <!-- Sidebar -->
        <div class="span-12 lg:span-4">
            <h3>Sidebar</h3>
            <p>Secondary content</p>
        </div>
    </div>
</div>
```

### **Complex Magazine Layout**

```html
<div class="container">
    <div class="grid">
        <!-- Header -->
        <header class="span-12">Header</header>
        
        <!-- Featured article -->
        <article class="span-12 md:span-8">
            <h2>Featured Article</h2>
        </article>
        
        <!-- Sidebar -->
        <aside class="span-12 md:span-4">
            <h3>Related Links</h3>
        </aside>
        
        <!-- Three equal columns -->
        <div class="span-12 lg:span-4">Article 1</div>
        <div class="span-12 lg:span-4">Article 2</div>
        <div class="span-12 lg:span-4">Article 3</div>
        
        <!-- Centered content -->
        <div class="span-10 start-2 lg:span-6 lg:start-4">
            <h3>Centered Content</h3>
        </div>
        
        <!-- Footer -->
        <footer class="span-12">Footer</footer>
    </div>
</div>
```

### **Card Grid Layout**

```html
<div class="container">
    <div class="grid">
        <!-- Cards: 1 col mobile, 2 cols tablet, 4 cols desktop -->
        <div class="span-12 md:span-6 xl:span-3">
            <div class="card">Card 1</div>
        </div>
        <div class="span-12 md:span-6 xl:span-3">
            <div class="card">Card 2</div>
        </div>
        <div class="span-12 md:span-6 xl:span-3">
            <div class="card">Card 3</div>
        </div>
        <div class="span-12 md:span-6 xl:span-3">
            <div class="card">Card 4</div>
        </div>
    </div>
</div>
```

## 🌐 Browser Support

### CSS Grid Support
- **Chrome 57+** ✅
- **Firefox 52+** ✅  
- **Safari 10.1+** ✅
- **Edge 16+** ✅
- **IE 11** ❌ (CSS Grid support is limited/buggy)

### CSS Custom Properties Support
- **Chrome 49+** ✅
- **Firefox 31+** ✅
- **Safari 9.1+** ✅  
- **Edge 15+** ✅
- **IE 11** ❌

### Fallback Strategy

For older browsers, you can provide flexbox fallbacks:

```css
/* Fallback for older browsers */
.grid {
  display: flex;
  flex-wrap: wrap;
}

.grid > * {
  flex: 1 1 auto;
}

/* Modern browsers with CSS Grid support */
@supports (display: grid) {
  .grid {
    display: grid;
    grid-template-columns: repeat(12, 1fr);
  }
  
  .grid > * {
    flex: none;
  }
}
```

## 🔧 Customization

### CSS Custom Properties

You can customize the grid system by overriding CSS custom properties:

```css
:root {
  --grid-gap: 2rem;        /* Increase gap between items */
  --grid-columns: 16;      /* Use 16 columns instead of 12 */
}

.container {
  --grid-gap: 0.5rem;      /* Smaller gap for specific container */
}
```

### Custom Breakpoints

Breakpoints are hardcoded in media queries, but you can modify them:

```css
/* Custom breakpoint values */
:root {
  --bp-sm: 576px;   /* Match Bootstrap's breakpoints */
  --bp-md: 768px;
  --bp-lg: 992px;
  --bp-xl: 1200px;
}

/* Note: You'll need to update the media queries manually */
@media (min-width: 576px) {
  .sm\:span-6 { grid-column-end: span 6; }
}
```

## 🎯 Best Practices

### **1. Mobile-First Approach**
Always start with mobile styles, then enhance for larger screens:

```html
<!-- ✅ Good: Mobile-first -->
<div class="span-12 md:span-6 lg:span-4">Content</div>

<!-- ❌ Avoid: Desktop-first -->
<div class="lg:span-4 md:span-6 span-12">Content</div>
```

### **2. Semantic HTML Structure**
Use appropriate HTML elements with grid classes:

```html
<!-- ✅ Good: Semantic structure -->
<main class="grid">
  <article class="span-8">Article</article>
  <aside class="span-4">Sidebar</aside>
</main>

<!-- ❌ Avoid: Div soup -->
<div class="grid">
  <div class="span-8">Article</div>
  <div class="span-4">Sidebar</div>
</div>
```

### **3. Consistent Spacing**
Use the built-in gap system rather than manual margins:

```html
<!-- ✅ Good: Use grid gap -->
<div class="grid">
  <div class="span-6">Content</div>
  <div class="span-6">Content</div>
</div>

<!-- ❌ Avoid: Manual spacing -->
<div class="grid" style="gap: 0;">
  <div class="span-6" style="margin-right: 1rem;">Content</div>
  <div class="span-6">Content</div>
</div>
```

### **4. Progressive Enhancement**
Design for the smallest screen first, then enhance:

```html
<!-- ✅ Good: Progressive enhancement -->
<div class="span-12 sm:span-6 lg:span-4">
  <!-- Works on all screens, optimized for larger ones -->
</div>
```

---

## 📚 Additional Resources

- [CSS Grid Complete Guide](https://css-tricks.com/snippets/css/complete-guide-grid/)
- [CSS Custom Properties Guide](https://developer.mozilla.org/en-US/docs/Web/CSS/Using_CSS_custom_properties)
- [Responsive Design Principles](https://web.dev/responsive-web-design-basics/)

---

**Built with ❤️ for modern web development** 