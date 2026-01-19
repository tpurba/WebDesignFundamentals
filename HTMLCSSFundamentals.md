# HTML CSS Fundamentals

## Semantic HTML (Accessibility Matters)

- Basically using the h1 or nav or header, HTML elements that will allow users without sight to be able to use screen reader and navigate the page
- **Rules to live by:**
  - One `<main>` per page
  - Headings must be in order (h1 → h2 → h3)
  - Buttons do actions, links navigate
  - Forms must use `<label>`
- **Receive:**
  - Keyboard support
  - Focus styles
  - Aria role for free

## Flexbox vs Grid (When to Use Each)

### Flexbox = one dimension
- Row or column
- Content-driven
- **Alignment-based**

### Grid = two dimensions
- Rows and columns
- Layout-driven
- **Structure-first: design layout**

### Flex box used when:
- Navbar
- Button groups
- Centering items
- Cards in a row
- Aligning icon + text

### Grid when:
- Page layouts
- Dashboards
- Forms
- Card grids
- Any matrix layout

## CSS Specificity & Cascade

- **CSS is rule based**
- **CSS applies style in this order**
  - Importance (!important)
  - Specificity (low→high)
    - `""` = 0
    - Element = 1
    - .class = 10
    - #id = 100
    - Inline style = 1000
  - Source order (last)

### Senior level css advice
- Avoid ids in CSS
- Avoid nesting selectors deeply
- Avoid !important unless utilities

### Tailwindcss benefit
- Avoids specificity wars
  - by using utility classes
  - Keeping specificity flat

## Responsive Design Without Media-Query Spam

- **Mobile-first mindset:**
  - Start small, scale up.
- **Even better: avoid media queries entirely**
  - Use flexible units
    - Width: min(100%, 600px)
  - Use grid magic:
    - `grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));`
  - Use clamp():
    - `font-size: clamp(1rem, 2vw, 1.5rem);`
  - Tailwind:
    - `<div class="grid grid-cols-1 md:grid-cols-3 gap-4">`
    - Only one breakpoint per tag

### Questions to ponder:
- Why is this layout fragile
- Aim for:
  - Fluid layouts
  - Content-driven sizing
  - Minimal overrides

## If You Use Tailwind, Still Learn:

### How it maps to real CSS
- Tailwind is not a layout system
- It is a class to css compiler
  - Every tailwind class = one or a few css declarations
  - Like p-4 maps to a p-4 class that has padding 1 rem

### Spacing scale:
```
p-1 → 0.25rem (4px)
p-2 → 0.5rem (8px)
p-4 → 1rem (16px)
p-8 → 2rem (32px)
```

### Why certain layouts break
- Its not tailwind that breaks but the css rule interacting
  - Like how justify-center doesn't work unless you use flex or grid

### Width + padding overflow:
- Happens due to setting the wrong class like w-full should be max-w-screen-xl-auto
- Height percentages only work if the parent has a height
  - If parent has height: auto child's height:100% won't working
  - Instead use min-h-screen for parent and then h-full

### H-full not working
- **Absolute positioning escapes container**
  - Looks for nearest ancestor
  - None exists falls back to body
  - **Fix:**
    - Add relative to parent

### Too many overrides
- Fragile layout design
- Let layouts handle it

