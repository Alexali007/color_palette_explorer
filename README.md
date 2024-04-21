# Color Palette Explorer

## Features
> Themes
> Simple usage
> Zero dependencies
> Multiple color representations
> Color comparison
> Opacity control
> Detail adjustments via mouse-wheel
> Responsive and auto-positioning
> Supports touch devices
> Swatches for quick-selection
> Fully accessible and i18n

## Browser
- jsdelivr
### Classic theme
> href="https://cdn.jsdelivr.net/npm/@simonwep/pickr/dist/themes/classic.min.css"
### Modern bundle
> src="https://cdn.jsdelivr.net/npm/@simonwep/pickr/dist/pickr.min.js"

## Usage
// Simple example, see optional options for more configuration.
const pickr = Pickr.create({
    el: '.color-picker',  // Selector or element which will be replaced with the actual color-picker.
    theme: 'classic', // or 'monolith', or 'nano'  // Which theme you want to use.
    // Optional color swatches. When null, swatches are disabled.
    // Types are all those which can be produced by pickr e.g. hex(a), hsv(a), hsl(a), rgb(a), cmyk, and also CSS color names like 'magenta'.
    // Example: swatches: ['#F44336', '#E91E63', '#9C27B0', '#673AB7']
    swatches: [
        'rgba(244, 67, 54, 1)',
        'rgba(233, 30, 99, 0.95)',
        'rgba(156, 39, 176, 0.9)',
        'rgba(103, 58, 183, 0.85)',
        'rgba(63, 81, 181, 0.8)',
        'rgba(33, 150, 243, 0.75)',
        'rgba(3, 169, 244, 0.7)',
        'rgba(0, 188, 212, 0.7)',
        'rgba(0, 150, 136, 0.75)',
        'rgba(76, 175, 80, 0.8)',
        'rgba(139, 195, 74, 0.85)',
        'rgba(205, 220, 57, 0.9)',
        'rgba(255, 235, 59, 0.95)',
        'rgba(255, 193, 7, 1)'
    ],
    // Show or hide specific components.
    // By default only the palette (and the save button) is visible.
    components: {

        // Main components
        preview: true,  // Display comparison between previous state and new color
        opacity: true,  // Display opacity slider
        hue: true,  // Display hue slider

        // Input / output Options
        interaction: {
            hex: true,  // hexadecimal representation of the rgba value
            rgba: true,  // red green blue and alpha
            hsla: true,  // hue saturation lightness and alpha
            hsva: true,  // hue saturation value and alpha
            cmyk: true,  // cyan mangenta yellow key
            input: true,  // Display input/output textbox which shows the selected color value
            clear: true,  // Display Clear Button; same as cancel, but keeps the window open
            save: true  // Display Save Button
        }
    }
});

## The HSVaColor object
- As default color representation is hsva (hue, saturation, value and alpha) used, but you can also convert it to other formats as listed below.
> hsva.toHSVA() - Converts the object to a hsva array.
> hsva.toHSLA() - Converts the object to a hsla array.
> hsva.toRGBA() - Converts the object to a rgba array.
> hsva.toHEXA() - Converts the object to a hexa-decimal array.
> hsva.toCMYK() - Converts the object to a cmyk array.
> hsva.clone() - Clones the color object.
- The toString() is overridden, so you can get a color representation string.
> hsva.toRGBA(); // Returns [r, g, b, a]
> hsva.toRGBA().toString(); // Returns rgba(r, g, b, a) with highest precision
> hsva.toRGBA().toString(3); // Returns rgba(r, g, b, a), rounded to the third decimal

## Methods
> pickr.on(event:String, cb:Function):Pickr - Appends an event listener to the given corresponding event-name (see section Events).

## Static Methods
> create(options:Object):Pickr - Creates a new instance.
