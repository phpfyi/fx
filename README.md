# FX - CSS Framework

![Code Language](https://img.shields.io/github/languages/top/phpfyi/fx)
![Code Size](https://img.shields.io/github/languages/code-size/phpfyi/fx)
![Commit Activity](https://img.shields.io/github/commit-activity/m/phpfyi/fx)
![Latest Commit](https://img.shields.io/github/last-commit/phpfyi/fx)

FX is a collection of CSS resets, classes, and mixins for rapidly building UI's across devices.

The goals of the project are as follows:

* To create a set of reset rules that take into account accessibly and create a consistent experience across devices and screen sizes.
* To create an extremely lightweight framework that is easy to extend.
* To abstract out common CSS rules into re-usable classes.
* To create a set of short but descriptive CSS classnames.
* To minimise the amount of work and HTML required to build layouts.

---

- [Installation](#installation)
- [CSS Reset](#css-reset)
- [CSS Classes](#css-classes)
  - [Breakpoints](#breakpoints)
  - [Alignment](#alignment)
  - [Clear](#clear)
  - [Columns](#columns)
  - [Container](#container)
  - [Display](#display)
  - [Flex](#flex)
  - [Float](#float)
  - [Margin](#margin)
  - [Padding](#padding)
  - [Position](#position)
  - [Text Align](#text-align)
  - [Vertical Height](#vertical-height)
  - [Visibility](#visibility)
  - [Width](#width)

---

## Installation

Require the FX framework package via composer.

```json
{
    "require": {
        "phpfyi/fx": "1.0.*"
    }
}
```

Create a copy of the FX config file with your custom config and import the core FX files.

If you wish to import specific parts of the framework please see the individual imported mixins, reset, and classes files.

```scss
@import 'config';

@import 'vendor/phpfyi/fx/core/mixins';
@import 'vendor/phpfyi/fx/core/reset';
@import 'vendor/phpfyi/fx/core/classes';
```

---

## CSS Reset

The FX framework contains sensible resets for common elements such as form elements.

---

## CSS Classes

### Breakpoints

The default breakpoint config is as follows and is appended to certain CSS classes to make them responsive.
Can be overidden with custom config.

```scss
$breakpoints: (
    "-xs": 480px,
    "-s": 600px,
    "-m": 768px,
    "-l": 960px,
    "-xl": 1200px,
    "-xxl": 1360px
);
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

Using columns across breakpoints.

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
.flex-xs /* flex child elements at xs breakpoint */
.flex-m /* flex child elements at m breakpoint */
...
```

There is also a class to reverse the flex layout of child elements across breakpoints.

```css
.flex-reverse /* flex reverse child elements */
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

Configure using $width-increments 

```scss
$width-increments: (0, 5, 10, 15, 20, 25, 30, 35, 40, 45, 50, 55, 60, 65, 70, 75, 80, 85, 90, 95, 100);
```

```css
.w-5 /* 5% width */
...
```