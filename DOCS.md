# Documentation

- [Installation](#installation)
- [Configuration](#configuration)
- [Responsive Breakpoints](#responsive-breakpoints)
  - [Responsive classes](#responsive-classes)
  - [Responsive mixins](#responsive-mixins)
- [Spacing](#spacing)
  - [Spacing utility classes](#spacing-utility-classes)
  - [Spacing mixins](#spacing-mixins)
- [Typography](#typography)
  - [Line heights](#line-heights)
  - [Typography utility classes](#typography-utility-classes)
  - [Typography mixins](#typography-mixins)
- [Grid](#grid)
  - [Container](#container)
  - [Rows](#rows)
  - [Columns](#columns)
  - [Grid examples](#grid-examples)
- [Buttons](#buttons)
  - [Button utility classes](#button-utility-classes)
    - [Button examples](#button-examples)
  - [Button mixins](#button-mixins)
    - [Button tips](#button-tips)
- [Optional Global Styles](#optional-global-styles)


## Installation

    npm install base-layers --save


## Configuration

Then, import it into your app's main SCSS file:

```scss
// app.scss

@import '~base-layers';

html {
  font-size: 100%;
}

body {
  line-height: 1.6;
}
```

You can also customize some values. The following are the default settings:

```scss
// app.scss

// Spacing
$spacer: 10px;

// Buttons
$btn-font: inherit;

$btn-primary-fg: #fff;
$btn-primary-bg: #f39;

$btn-secondary-fg: #fff;
$btn-secondary-bg: #3d15b9;

$btn-tertiary-fg: #fff;
$btn-tertiary-bg: #15b98c;

$btn-disabled-opacity: 0.65;
$btn-border-radius: 4px;

// Typography
  // 1.067 — Minor Second
  // 1.125 — Major Second
  // 1.200 — Minor Third
  // 1.250 — Major Third
  // 1.333 — Perfect Fourth
  // 1.414 — Augmented Fourth
  // 1.500 — Perfect Fifth
  // 1.618 — Golden Ratio
$type-scale: 1.250;

// RWD Breakpoints
$breakpoint-sm: 576px;
$breakpoint-md: 768px;
$breakpoint-lg: 992px;
$breakpoint-xl: 1200px;

// Grid
$grid-container-width: 1440px;
$grid-gutter: 16px;
$grid-column-count: 12;

@import '~base-layers';

html {
  font-size: 100%;
}

body {
  line-height: 1.6;
}
```

See the [`_default-values.scss`](https://github.com/tinacious/base-layers/blob/main/scss/_default-values.scss) file for all available overrides.

Alternatively, you can choose to include only the modules of your choice. See [`base-layers.scss`](https://github.com/tinacious/base-layers/blob/main/scss/base-layers.scss) for available modules.


## Responsive Breakpoints

**Base Layers** is mobile-first so all the default classes apply to the smallest screen size.

The following breakpoints are supported and configurable:

- `sm`
- `md`
- `lg`
- `xl`

### Responsive classes

Each part of the framework has varying support for breakpoints. See each relevant section for related responsive classes.


### Responsive mixins

There are some mixins available to help use the breakpoints:

```scss
@include breakpoint-up(breakpoint) {
  // content for the provided breakpoint and larger
}

@include breakpoint-down(breakpoint) {
  // content for the provided breakpoint and smaller
}
```

## Spacing

Utility classes for applying padding and margins to elements.

Set the `$spacer` value (default: 10px) and use the multipliers.

Apply margins or padding to:

- individual sides, one at a time
- all sides
- horizontal sides (left and right)
- vertical sides (top and bottom)

### Spacing utility classes

Spacing utility classes use the following pattern:

```
<property><side>-<n>
```

Here are the classes you can apply to your HTML:

```scss
// Padding
    // Individual sides
    .pt-0 -> .pt-20
    .pr-0 -> .pr-20
    .pb-0 -> .pb-20
    .pl-0 -> .pl-20

    // Multiple sides
    .p-0  -> .p-20   // all
    .pv-0 -> .pv-20  // vertical
    .ph-0 -> .ph-20  // horizontal

// Margins
    // Individual sides
    .mt-0 -> .mt-20
    .mr-0 -> .mr-20
    .mb-0 -> .mb-20
    .ml-0 -> .ml-20

    // Multiple sides
    .m-0  -> .m-20   // all
    .mv-0 -> .mv-20  // vertical
    .mh-0 -> .mh-20  // horizontal
```

Breakpoints are supported and use the following pattern:

```
<property><side>-<breakpoint>-<n>
```

So it's the same as above except with an extra `-breakpoint-` value:

```scss
// Padding
    // Individual sides
    .pt-md-0 -> .pt-md-20
    .pr-md-0 -> .pr-md-20
    .pb-md-0 -> .pb-md-20
    .pl-md-0 -> .pl-md-20

    // Multiple sides
    .p-md-0  -> .p-md-20   // all
    .pv-md-0 -> .pv-md-20  // vertical
    .ph-md-0 -> .ph-md-20  // horizontal

// Margins
    // Individual sides
    .mt-md-0 -> .mt-md-20
    .mr-md-0 -> .mr-md-20
    .mb-md-0 -> .mb-md-20
    .ml-md-0 -> .ml-md-20

    // Multiple sides
    .m-md-0  -> .m-md-20   // all
    .mv-md-0 -> .mv-md-20  // vertical
    .mh-md-0 -> .mh-md-20  // horizontal
```

### Spacing mixins

There are no mixins for spacing and you wouuld have to define each `margin` and `padding` value yourself.

```scss
.box {
  padding: $spacer * 2;
}
```

If `$spacer` is 10px then this would output to the following:

```css
.box { padding: 20px; }
```


## Typography

Font sizes are generated using a type scale and are based off of the font size of the document.

<img src="https://github.com/tinacious/base-layers/raw/main/assets/typography.png">

Here are some suggested type scales:

- 1.067 — Minor Second
- 1.125 — Major Second
- 1.200 — Minor Third
- **1.250 — Major Third (default)**
- 1.333 — Perfect Fourth
- 1.414 — Augmented Fourth
- 1.500 — Perfect Fifth
- 1.618 — Golden Ratio

It's recommended, for accessibility reasons, to set the font as follows:

```scss
html {
  font-size: 100%;
}
```

**Base Layers** makes no assumptions about your heading sizes, i.e. it does **not** assume that your `h1`'s will be huge.

**Base Layers** takes a semantic approach, requiring you to specify your font sizes yourself for your headings how you prefer, either globally or on an as-needed basis.

The following sizes are supported:

- `xxxs`
- `xxs`
- `xs`
- **`sm`** (default, 100%)
- `md`
- `lg`
- `xl`
- `xxl`
- `xxxl`


### Line heights

It's recommended to add a `line-height` to the body:

```scss
body {
  line-height: 1.6;  // ~1.4 - 1.7
}
```

Line heights are adjusted for sizes `lg` and up to `1.15`.


### Typography utility classes

Utility classes follow this pattern:

    .text--<size>

The following classes are available:

    .text--xxxs
    .text--xxs
    .text--xs
    .text--sm (default)
    .text--md
    .text--lg
    .text--xl
    .text--xxl
    .text--xxxl

Those apply to all breakpoints. The pattern is as follows:

    .text--bp-<breakpoint>--<size>

So it is very similar except it has an extra `--bp-XX--` value.

To get text that is XXL only on the XL breakpoint, you would use the following:

    .text--bp-xl--xxl


### Typography mixins

There are similar mixins available:

```scss
@include text-xxxs;
@include text-xxs;
@include text-xs;
@include text-sm; // default
@include text-md;
@include text-lg;
@include text-xl;
@include text-xxl;
@include text-xxxl;
```

## Grid

The grid has 12 columns by default but this can be configured along with the gutter width.

<img src="https://github.com/tinacious/base-layers/raw/main/assets/grid.png">

Grids have the following structure:

- container
  - row
    - column

### Container

The `.container` is optional and sets a max-width. If you want a full-span grid, you can omit it and just use any `div`.


### Rows

Your columns need to go in rows.


### Columns

The grid uses a mobile-first approach. The column classes are as follows:

```scss
.col-xs-12
.col-12   // alias for .col-xs-N
```

### Grid examples

Let's say on mobile you want your elements stacked, and on the medium breakpoint and larger you want them in 2-columns (one main area, one sidebar), you can do the following options.

For a grid with a container and a max width:

```html
<div class="container">
  <div class="row">
    <div class="col-xs-12 col-md-8">
        Main area
    </div>

    <div class="col-xs-12 col-md-4">
        Sidebar
    </div>
  </div>
</div>
```

For a full-width grid, just omit the `.container`:

```html
<div class="row">
  <div class="col-xs-12 col-md-8">
    Main area
  </div>

  <div class="col-xs-12 col-md-4">
    Sidebar
  </div>
</div>
```

Get the [Chrome extension](https://github.com/tinacious/base-layers-chrome) to toggle a grid overlay.


## Buttons

**Base Layers** provides a reasonable default button style.

<img src="https://github.com/tinacious/base-layers/raw/main/assets/buttons.png" width="330px">

By default, there are no button styles applied (unless you also import `globals.scss`). You can use the following button classes and mixins to style the desired elements.

### Button utility classes

```scss
.btn

.btn--primary
.btn--secondary
.btn--tertiary
.btn--disabled
```

#### Button examples

```html
<button class="btn btn--primary">
  Click me
</button>

<button class="btn btn--secondary btn--disabled">
  Nope, can't touch this!
</button>
```

### Button mixins

There are similar mixins available:

```scss
@include btn;

@include btn--primary;
@include btn--secondary;
@include btn--tertiary;
@include btn--disabled;
```

There is also a handy mixin to remove all default user agent button styles:

```scss
@include btn--unstyled;
```

#### Button tips

If you'd like to make buttons larger or smaller, combine them with text classes or utilities. The padding is dynamic and scales with the font size to maintain the same aspect ratio.

```html
<button class="btn btn--tertiary text--xl">
  Sign Up
</button>

<button class="btn text--xs">
  Cancel
</button>
```

<img src="https://github.com/tinacious/base-layers/raw/main/assets/button-text-size.png" width="317px" />

## Optional Global Styles

Some reasonable defaults have been provided as an **optional** import but are not included by default. They include styles for the following:

| HTML tag   | Styles applied                                    |
| ---------- | ------------------------------------------------- |
| `<p>`      | Paragraphs have default vertical margins of `1em` |
| `<strong>` | Bold text, e.g. **test**                          |
| `<em>`     | Italic text, e.g. _test_                          |
| `<button>` | [Button styles](#buttons) described above         |

To use the globals, import them:

```scss
// app.scss

// ... override defaults ...

@import '~base-layers';
@import '~base-layers/scss/globals'; // or globals -> globals.scss
```
