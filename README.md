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

## License

This module is licensed under the MIT License. See the LICENSE file for more information.
