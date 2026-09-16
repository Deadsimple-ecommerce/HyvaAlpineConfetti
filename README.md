# Deadsimple Hyva Alpine Confetti

This module integrates the [Alpine Confetti](https://github.com/jackwh/alpine-confetti) library with Magento 2 and Hyvä themes. It bundles the [canvas-confetti](https://www.npmjs.com/package/canvas-confetti) functionality and exposes Alpine magic helpers that you can trigger directly from templates.

## Installation

1. Install the module with Composer:

```bash
composer require deadsimple/hyva-alpine-confetti
```

2. Enable the Magento module:

```bash
bin/magento module:enable Deadsimple_HyvaAlpineConfetti
```

3. Run setup upgrade:

```bash
bin/magento setup:upgrade
```

## Usage

Once enabled, the module registers Alpine magic helpers that fire confetti from the element that triggered the event.

### Basic confetti

```html
<button x-on:click="$confetti()">Celebrate</button>
```

### Custom confetti burst

```html
<button
  x-on:click="$confetti({ particleCount: 250, spread: 160, startVelocity: 35 })"
>
  Launch confetti
</button>
```

### Starburst effect

```html
<button x-on:click="$starburst()">Starburst</button>
```

### Emoji confetti

```html
<button x-on:click="$emojify(['🎉', '✨', '🎊'], 25)">Party</button>
```

The helpers accept either a number of particles or a config object, so you can easily fine-tune the look and behavior for sale banners, success states, or celebratory interactions.

## Configuration

All methods accept the full range of [canvas-confetti options](https://github.com/catdad/canvas-confetti?tab=readme-ov-file#options). Here's a quick reference for the most commonly used ones:

```javascript
{
    particleCount: 100, // Number of particles
    angle: 90,          // Direction in degrees
    spread: 45,         // Spread in degrees
    startVelocity: 45,  // Initial velocity
    decay: 0.9,         // Particle decay rate
    gravity: 1,         // Gravity strength
    drift: 0,           // Side-to-side drift
    ticks: 200,         // Particle lifetime
    colors: ['#fff'],   // Color array
    scalar: 1           // Size multiplier
}
```

The plugin respects the `prefers-reduced-motion` media query by default. Users with motion sensitivity won't see the animations.

## Credits

- 🎊 [canvas-confetti](https://github.com/catdad/canvas-confetti)
- ⛰️ [Alpine.js](https://alpinejs.dev)
- 😎 [Jack Webb-Heller](https://github.com/jackwh)

## License

This module is licensed under the MIT License. See the LICENSE file for more information.
