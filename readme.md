# PostCSS Custom Properties
[![Build Status][ci-img]][ci]

[PostCSS] plugin to define and use custom properties. Not to be confused with the CSS Custom Properties specification which are really variables.

[PostCSS]: https://github.com/postcss/postcss
[ci-img]:  https://travis-ci.org/daleeidd/postcss-define-property.svg
[ci]:      https://travis-ci.org/daleeidd/postcss-define-property

NOTE: Must be used before any plugin that uses the `$` for variables.

```css
/* Input */
size: $height $width {
  height: $height;
  width: $width;
}

size: $size {
  height: $size;
  width: $size;
}

.rectangle {
  size: 50px 100px;
}

.square {
  size: 50px;
}
```

```css
/* Output */
.rectangle {
  height: 50px;
  width: 100px;
}

.square {
  height: 50px;
  width: 50px;
}
```

There must be a minimum of one space after the semicolon for property definitions; otherwise, it will just appear as a
psuedo-selector.

Properties – including native ones – can be redefined. The placement of property definitions matter as they are not hoisted.

Properties can also be overloaded as the parameter quantity forms part of the property's signature.

## Usage

```js
postcss([ require('postcss-define-property') ])
```

See [PostCSS] docs for examples for your environment.
