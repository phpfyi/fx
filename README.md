# FX - CSS Framework

FX is a lightweight SCSS framework with a grid system and set of utility classes for rapidly building UI's

![Code Language](https://img.shields.io/github/languages/top/phpfyi/fx)
![Code Size](https://img.shields.io/github/languages/code-size/phpfyi/fx)
![Commit Activity](https://img.shields.io/github/commit-activity/m/phpfyi/fx)
![Latest Commit](https://img.shields.io/github/last-commit/phpfyi/fx)

---
- [Installation](#installation)
  - [NPM](#npm)
  - [Composer](#composer)
  - [Generated files](#generated-files)
  - [Required Imports](#required-imports)
  - [_config.scss File](#_configscss-file)
  - [app.scss File](#appscss-file)
- [FX Mixins](#fx-mixins)
- [FX Utilities](#fx-utilities)

---

## Installation

### NPM

Add the FX framework as a dev dependency

```console
npm i https://github.com/phpfyi/fx --save-dev
```

Copy the FX core files into your local SASS folder (adjust the destination to suit your project)

```console
cp -R  node_modules/fx/src/core src/assets/scss
```

### Composer

Require the FX framework package via composer.

```console
composer require phpfyi/fx
```

Copy the FX core files into your local SASS folder (adjust the destination to suit your project)

```console
cp -R  vendor/phpfyi/fx/src/core src/assets/scss
```

### Generated files

After running the cp command a number of files and folders are generated

- ***app.scss*** - main app SCSS file
- ***_config.scss*** - var configuration file
- ***_mixins.scss*** - mixin imports files
- ***app/*** - app imports
- ***mixins/*** - app mixins

### Required Imports

FX requires 4 files to be loaded globally before any other SCSS. Your application configuration and mixins (generated from the cp command above), and the FX functions and mixins.

#### Manual

You can import these manually if required.

```scss
@import "@/assets/scss/_config.scss"; 
@import "@/assets/scss/_mixins.scss"; 
@import "~fx/src/_functions.scss";
@import "~fx/src/_mixins.scss";
```

#### Vue

If using Vue you can add the following to vue.config.js

```javascript
module.exports = {
    css: {
        loaderOptions: {
            sass: {
                additionalData: `
                    @import "@/assets/scss/_config.scss"; 
                    @import "@/assets/scss/_mixins.scss"; 
                    @import "~fx/src/_functions.scss";
                    @import "~fx/src/_mixins.scss";
                `,
            },
        },
    },
}
```

### _config.scss File

The _config.scss file is used both in FX SCSS files and you app SCSS files to create things like the grid system and default styles.

```scss
////////////////////////////////////////////////////////////////////////////////
// GRID
////////////////////////////////////////////////////////////////////////////////

$breakpoints: (
  "": 0px,
  "-xs": 480px,
  "-s": 600px,
  "-m": 768px,
  "-l": 960px,
  "-xl": 1200px,
  "-xxl": 1360px,
);

$columns: 12;

$container-max: 1220px;

////////////////////////////////////////////////////////////////////////////////
// FONT
////////////////////////////////////////////////////////////////////////////////

$font-heading: "Lato", sans-serif;
$font-body: "Lato", sans-serif;
$font-code: monospace;

$font-family: $font-body;
$font-size: 18px;
$font-weight: 400;
$line-height: 28px;

$font-weights: (300, 400, 500, 600, 700);

////////////////////////////////////////////////////////////////////////////////
// COLORS
////////////////////////////////////////////////////////////////////////////////

$colors: (
   "black": #000,
   "white": #fff,
   "grey-xxl": #F7F7F7,
   "grey-xl": #ececec,
   "grey-l": #CCC,
   "grey-m": #999,
   "grey-d": #666,
   "grey-xd": #333,
   "grey-xxd": #232323,
   "grey-xxxd": #171717,
);

////////////////////////////////////////////////////////////////////////////////
// IMAGES
////////////////////////////////////////////////////////////////////////////////

$img: "/img/";

////////////////////////////////////////////////////////////////////////////////
// BOX
////////////////////////////////////////////////////////////////////////////////

$padding: (0, 5, 10, 15, 20, 25, 30, 40, 50);

$margins: (0, 5, 10, 15, 20, 25);

$widths: (0, 5, 10, 15, 20, 25, 30, 35, 40, 45, 50, 55, 60, 65, 70, 75, 80, 85, 90, 95, 100);

$heights: (0, 20, 40, 60, 80, 100);

////////////////////////////////////////////////////////////////////////////////
// POSITION
////////////////////////////////////////////////////////////////////////////////

$z-indexes: (0, 1, 2, 3, 4, 5);
```

## app.scss File

The app.scss file is created with the following imports. These provide a CSS reset, access to the FX utility classes, and a scaffold to quickly customize key CSS styling.

```scss
// fx
@import "~fx/src/reset";
@import "~fx/src/utilities";

// app
@import "app/body";
@import "app/card";
@import "app/code";
@import "app/form";
@import "app/heading";
@import "app/hr";
@import "app/_input-button";
@import "app/_input-checkbox";
@import "app/_input-radio";
@import "app/_input-select";
@import "app/_input-textarea";
@import "app/_input";
@import "app/_label";
@import "app/link";
@import "app/list";
@import "app/paragraph";
@import "app/table";
@import "app/text";
```

## FX Mixins

FX provides handy mixins to streamline workflow and cut out a lot of boilerplate code. A number of these mixins will add required cross browser prefixes as well as validate passed values against your configuration. e.g colors are present in the $colors array.

***See src/mixins for more detail and the generated CSS***

```scss
@mixin animation($value)

@mixin appearance($value: none)

@mixin bg-color($color)
@mixin bg-opacity($color)

@mixin border-radius($size)

@mixin box-shadow($x: 0, $y: 0, $blur: 2px, $color: #666)
@mixin box-sizing($value: border-box)

@mixin button

@mixin color($color)

@mixin flex 

@mixin gradient-v($from: 0%, $start: '#FFF', $to: 100%, $stop: #000)

@mixin hover-underline

@mixin indent-hidden

@mixin input

@mixin keyframes($name)

@mixin min-width($breakpoint: "")

@mixin position($position: absolute, $z-index: 0, $top: auto, $right: auto, $bottom: auto, $left: auto)
@mixin position-relative($z-index: 0, $top: auto, $right: auto, $bottom: auto, $left: auto)
@mixin position-fixed($z-index: 0, $top: auto, $right: auto, $bottom: auto, $left: auto)
@mixin position-absolute($z-index: 0, $top: auto, $right: auto, $bottom: auto, $left: auto)

@mixin prefix($key, $value)

@mixin rotate($degrees)

@mixin scroll-x 
@mixin scroll-y

@mixin square($size)
@mixin circle($size) 

@mixin transform($value)

@mixin transition($property: all, $time: 500ms, $method: ease-in-out)
```

## FX Utilities

```scss
.align-h // align horizontal

.box-shadow // add box shadow

.cl // clear left
.cr // clear right
.cb // clear both
.ca // clear after

.col-12 // columns
.col-12-m // columns at breakpoint

.container // container
.container-s // container max-width is breakpoint

.block // display block
.inline // display inline
.inline-block // display inline-block
.hide // display none

.flex-items-c // align inner items center
.flex-items-h // align inner items horizontal
.flex-items-v // align inner items vertical
.flex-items-end // align inner items to end

.flex-reverse // reverse direction
.flex-reverse-m // reverse direction at breakpoint

.flex-fill // flex 1
.flex-grow // flex grow
.flex-shrink // dont't stretch
.flex-column // flex direction column

.flex // display flex
.flex-m // display flex at breakpoint

.fl // float left
.fr // float right

.font-body // $font-body style
.font-heading // $font-heading style
.font-code // $font-code style
.font-uppercase // uppercase text
.font-italic // italic text
.font-600 // font weight

.img-stretch // file height and width

.mm // 10px margin
.mar-10 // margin by size
.mar-10-h // horizontal margin by size
.mar-10-v // vertical margin by size

.overflow-hidden // hide overflow

.pp // 10px padding
.pad-10 // padding by size
.pad-10-h // horizontal padding by size
.pad-10-v // vertical padding by size

.relative // relative position
.absolute // absolute position
.absolute-c // absolute position and centered
.absolute-v // absolute position and centered vertically

.h-100 // height by percent
.vh-100 // vertical height by percent
.w-100 // width by percent

.color-grey-l // color from $colors config
.bg-grey-l // background color from $colors config

.txt-c // center aligned text
.txt-l // left aligned text
.txt-r // right aligned text

.underline-hover // underline on hover
.underline-none // remove text decoration

.invisible // visibility hidden
.visible // visibility visible

.z-1 // z-index from $z-indexes config
```

### Legacy

Renamed in v2

```scss
.position-absolute // absolute position
.position-absolute-c // absolute position and centered
.position-absolute-v // absolute position and centered vertically

.mar-h-10 // horizontal padding by size
.mar-v-10 // vertical padding by size

.pad-h-10 // horizontal padding by size
.pad-v-10 // vertical padding by size

.hover-underline // underline on hover
.no-underline // remove text decoration
```