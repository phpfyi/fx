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
- [Global Styles](#global-styles)
  - [Manual](#manual)
  - [Vue](#vue)
- [App Styles](#app-styles)
- [Configuration](#configuration)
- [FX mixins](#fx-mixins)
- [FX utilities](#fx-utilities)

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

## Global Styles

### Manual

FX requires 4 files to be loaded globally before any other SCSS. Your application configuration and mixins (generated from the cp command above), and the FX functions and mixins.

```scss
@import "@/assets/scss/_config.scss"; 
@import "@/assets/scss/_mixins.scss"; 
@import "~fx/src/_functions.scss";
@import "~fx/src/_mixins.scss";
```

### Vue

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

## App Styles

After running the cp command an app.scss file is created with the following imports. These provide a CSS reset, access to the FX utility classes, and a scaffold to quickly customize key CSS styling.

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

## Configuration

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

## FX mixins

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







### Alignment

Align flex and non flex elements.

```css
.align-c /* flex align items to center */
.align-v /* flex align items vertically */
.align-h /* align element horizontally */
.align-h-r /* flex align items horizontally and to the right */
```

### Clear

Used to clear floated elements.

```css
.cl /* clear left */
.cr /* clear right */
.cb /* clear both */
```

### Columns

Used to create column layouts.
Columns should be inside an element with a container class (or another flex element)

Configure using $columns

```scss
$columns: 12;
```

```css
.col-1 /* 1/12 width */
.col-6 /* 1/2 width */
.col-12 /* 100% width */
...
```

Using columns with breakpoints.

```scss
$breakpoints: (...
```

```css
.col-1-xs /* 1/12 width at xs breakpoint */
.col-6-m /* 1/2 width at m breakpoint  */
.col-12-xl /* 100% width at xl breakpoint  */
...
```

### Container

Container elements can be used to create fixed centered elements with a variable number of child columns.

```css
.container /* full width flex container */
```

Using containers with breakpoints.

```scss
$breakpoints: (...
```

```css
.container-xs /* xs width centered flex container */
.container-m /* m width centered flex container */
...
```

### Display

Display classes can show / hide elements based on the CSS display / visibility rules.

```css
.block /* display block */
.inline /* display inline */
.inline-block /* display inline-block */
.hide /* display none */
```

### Flex

Used to turn an element into a flex container for child elements.
Container classes already have flex rules applied.
Use col classes on child elements of flex.

```css
.flex /* flex child elements */
```

Using flex with breakpoints.

```scss
$breakpoints: (...
```

```css
.flex-xs /* flex child elements at xs breakpoint */
.flex-m /* flex child elements at m breakpoint */
...
```

There is also a class to reverse the flex layout of child elements.

```css
.flex-reverse /* flex reverse child elements */
```

Using flex reverse with breakpoints.

```scss
$breakpoints: (...
```

```css
.flex-reverse-xs /* flex reverse child elements at xs breakpoint */
.flex-reverse-m /* flex reverse child elements at m breakpoint */
...
```

## Float

Used to float elements.

```css
.fl /* float left */
.fr /* float right */
```

## Margin

Used to add / remove margins around elements.

Configure using $margin-increments 

```scss
$margin-increments: (0, 5, 10, 15, 20, 25);
```

```css
.mar-5 /* adds 5px margin around elements */
.mar-h-5 /* adds 5px margin left and right around elements - horizontal */
.mar-v-5 /* adds 5px margin top and bottom around elements - vertical */
...
```

## Padding

Used to add / remove padding around elements.

Configure using $padding-increments 

```scss
$padding-increments: (0, 5, 10, 15, 20, 25);
```

```css
.pad-5 /* adds 5px padding around elements */
.pad-h-5 /* adds 5px padding left and right around elements - horizontal */
.pad-v-5 /* adds 5px padding top and bottom around elements - vertical */
...
```

## Position

Used to make elements absolute and relative positioned.

```css
.position-c /* absolute positioned with a z-index of 1 and centered */
.position-v /* absolute positioned with a z-index of 1 and centered vertically */
.relative /* relative positioned with a z-index of 0 */
```

## Text Align

Used to align text elements across breakpoints.

```css
.txt-l /* aligns text left */
.txt-r /* aligns text right */
.txt-c /* aligns text center */
```

Using text align with breakpoints.

```scss
$breakpoints: (...
```

```css
.txt-l-xs /* aligns text left at xs breakpoint */
.txt-l-m /* aligns text left at m breakpoint */
...
```

## Vertical Height

Used to define the vertical height on an element.

Configure using $height-increments 

```scss
$height-increments: (0, 20, 40, 60, 80, 100);
```

```css
.vh-20 /* 20% height */
...
```

## Visibility

Used to change element visibility.

```css
.visible /* visibility visible */
.invisible /* visibility hidden */
```

## Width

Used to set an elements width.

Configure using $widths 

```scss
$widths: (0, 5, 10, 15, 20, 25, 30, 35, 40, 45, 50, 55, 60, 65, 70, 75, 80, 85, 90, 95, 100);
```

```css
.w-5 /* 5% width */
...
```