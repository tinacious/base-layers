
# Base Layers

> The foundation of your website's outfit 👙🩲

<img width="300px" src="https://github.com/tinacious/base-layers/raw/main/assets/tank-top.png" />

- [About Base Layers](#about-base-layers)
  - [What's included?](#whats-included)
    - [Namespacing](#namespacing)
- [Usage](#usage)
  - [Installation](#installation)
  - [API Documentation](#api-documentation)
- [Design Resources](#design-resources)


![Sass (SCSS) CI](https://github.com/tinacious/base-layers/workflows/Sass%20(SCSS)%20CI/badge.svg)

## About Base Layers

**Base Layers** provides utility classes and Sass mixins (SCSS) to help you build out your site.

**Base Layers** is geared towards front-end developers that want a little something to help with commonly-repeated styles but that don't want an existing theme or design as opinionated as Bootstrap or Material UI.

First, it strips away all your styles (using [Eric Meyer's CSS reset](https://meyerweb.com/eric/tools/css/reset/)). Next, it gives you some basics to help get you ready for your day of web development. The rest is up to you!

It's like the tank top that you wear under your hoodie. It isn't the main outfit.

No blouses, no ties, and **definitely no fedoras**. It isn't your website's outfit, it's your website's base layers.


### What's included?

Base Layers provides **CSS utility classes** ([BEM](https://blog.tinaciousdesign.com/bem-css-scalable-maintainable) style, with double-kebab (`--`) modifiers) and **Sass mixins** to help get you ready for your day of coding.

Utilities to help you with:

- a configurable, responsive grid
- spacing elements, including margins and padding
  - supports namespacing
- styling buttons
- typography utilities
  - supports namespacing
- responsive design utilities


#### Namespacing

Using the namespace mixins is one strategy to leverage the framework while building an embedded web application, for example, a Chrome extension that injects UI onto a website in a way to make sure you are using a unique prefix for your class names. For example, instead of `p-1` you would get `my-app-u-p-1` if you used the namespace `my-app-u-`. See the [documentation](https://github.com/tinacious/base-layers/blob/main/DOCS.md) for specifics.


## Usage

### Installation

    npm install base-layers --save

### API Documentation

Read the [documentation](https://github.com/tinacious/base-layers/blob/main/DOCS.md).


## Design Resources

Some Figma frames with grid styles have been created to help make designer-developer collaboration faster.

🎨 [Access the Figma project here](https://www.figma.com/file/p0c41xkunDsLZ67VWJZtFk/Grid)
