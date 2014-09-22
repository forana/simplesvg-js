# simplesvg-js

A very bare-bones SVG-generating library for browser usage.

## Installing

`bower install simplesvg-js` or just throw [simplesvg.js](https://raw.githubusercontent.com/forana/simplesvg-js/master/simplesvg.js) from this repo into your project somewhere.

## Methods

Each one of these methods takes an optional `attrs` parameter - this is an object whose properties will be bound as attributes to the corresponding created object.

### (`window.`)`SimpleSVG([attrs])`

Creates and returns an SVG element. Useful (read: necessary) attributes to set here are `width` and `height`, both pixel (`px`) values.

The remaining methods operate on this returned element, and return the same element for chaining purposes. All coordinates are numeric and absolute - no `px` required.

### `.circle(x, y, r, [attrs])`

Creates a circle at coordinates (`x`, `y`) with radius `r`.

### `.rectangle(x, y, width, height, [attrs])`

Creates a reactangle with upper-left corner at (`x`, `y`) with `width` and `height`.

### `.line(x1, y1, x2, y2, [attrs])`

Creates a line from (`x1`, `y1`) to (`x2`, `y2`).

### `.path(points, closed, [attrs])`

Creates a shape consisting of coordinates in the `points` array (each item being a 2-item array of the form `[x, y]`. If `closed`, the path will be closed (and thus eligible to have a `fill`).

### `.text(string, x, y, [attrs])`

Creates a text node with the contents `string` with the baseline starting at (`x`, `y`).

### `.defaults(attrs)`

Sets default `attrs`. All subsequent method calls on this `svg` element will have those `attrs` applied, before any passed `attrs` (so passed overrides default). The `attrs` passed into this method will be 'inherited' into the existing defaults - any pre-existing properties not overridden by the passed `attrs` will still be set.

### `.clearDefaults(attrs)`

Clear out any set defaults.

## An Example

Check out [index.html](https://raw.githubusercontent.com/forana/simplesvg-js/master/index.html) for an example of using this, with a small amount of CSS interaction.

## License
MIT
