# OWLCarouselVanilla 🦉

**OWLCarouselVanilla** is a modern, high-fidelity, zero-dependency Vanilla JavaScript carousel. It achieves full feature parity with the famous Owl Carousel 2 while eliminating jQuery dependencies, providing a premium, lightweight, and extremely customizable experience for modern web development.

![OWLCarouselVanilla Demo](https://images.unsplash.com/photo-1544947950-fa07a98d237f?q=80&w=1200&auto=format&fit=crop)

## ✨ Premium Features

- **🚀 Zero Dependencies**: 100% Native ES6+ JavaScript.
- **🏗️ Full Parity**: Supports `stagePadding`, `merge`, `autoWidth`, `autoHeight`, `RTL`, and more.
- **🎨 UI Positions**: Advanced positioning system for Nav and Dots (Top, Middle, Bottom, Vertical stacks).
- **🕹️ Responsive Grid**: Breakpoint-based settings with deep object merging.
- **⚡ Performance**: Hardware-accelerated transitions (`translate3d`) and optimized DOM recycling.
- **📱 Touch & Drag**: Native support for mouse drag and touch gestures with elastic `pullDrag`.
- **🎭 Animations**: Built-in support for custom entrance and exit animations (Animate.css compatible).

## 🚀 Installation

Include the core files in your project:

```html
<!-- Core Structural Styles -->
<link rel="stylesheet" href="css/owlcarouselvanilla.css">

<!-- Optional Demo/Theme Styles -->
<link rel="stylesheet" href="css/style.css">

<!-- Core Script -->
<script src="js/owlcarouselvanilla.js"></script>
```

## 🛠️ Basic Usage

```html
<div class="owl-carousel" id="main-slider">
    <div class="item"><h4>Slide 1</h4></div>
    <div class="item"><h4>Slide 2</h4></div>
    <div class="item"><h4>Slide 3</h4></div>
</div>

<script>
    new OwlCarouselVanilla('#main-slider', {
        items: 3,
        loop: true,
        margin: 20,
        nav: true,
        dots: true,
        responsive: {
            0: { items: 1 },
            768: { items: 2 },
            1024: { items: 3 }
        }
    });
</script>
```

## ⚙️ Configuration Options

| Option | Type | Default | Description |
| :--- | :--- | :--- | :--- |
| `items` | Number | `3` | Number of items to display. |
| `margin` | Number | `0` | Margin-right on items (px). |
| `loop` | Boolean | `true` | Infinite loop. |
| `rewind` | Boolean | `false` | Go back to start when at end (only if `loop` is false). |
| `center` | Boolean | `false` | Center item. Works with odd and even items. |
| `stagePadding` | Number | `0` | Padding left/right on stage (peek neighbors). |
| `merge` | Boolean | `false` | Merge items based on `data-merge` attribute. |
| `autoWidth` | Boolean | `false` | Use item's natural width. |
| `autoHeight` | Boolean | `false` | Adjust height based on active slide. |
| `nav` | Boolean | `false` | Show Next/Prev buttons. |
| `navPosition` | String | `'middle-left-right'` | `top-left`, `top-center`, `top-right`, `bottom-left`, `bottom-center`, `bottom-right`, `left-vertical`, `right-vertical`. |
| `dots` | Boolean | `true` | Show dots navigation. |
| `dotsPosition` | String | `'bottom-center'` | Same options as `navPosition`. |
| `autoplay` | Boolean | `false` | Autoplay support. |
| `rtl` | Boolean | `false` | Right-to-left support. |
| `pullDrag` | Boolean | `true` | Elastic effect when dragging past limits. |

## 🌟 Advanced Features

### Merge Grid
Items can occupy multiple columns using the `data-merge` attribute:
```html
<div class="item" data-merge="2">Ocupo 2 colunas</div>
```

### Stage Padding
Reveal parts of the next and previous slides:
```javascript
new OwlCarouselVanilla('.owl-carousel', {
    stagePadding: 50,
    margin: 10
});
```

### Custom Animations
Use standard CSS classes for slide transitions:
```javascript
new OwlCarouselVanilla('.owl-carousel', {
    animateOut: 'fadeOut',
    animateIn: 'flipInX',
    items: 1
});
```

## 📡 API & Callbacks
```javascript
const owl = new OwlCarouselVanilla('#slider', {
    onInitialized: () => console.log('Ready!'),
    onTranslated: (event) => console.log('Moved to:', event.index)
});

owl.next();
owl.to(5);
owl.refresh(); // Recalculate everything
```

## 📄 License
MIT License. Created by [Uziel](https://github.com/uzielweb).
