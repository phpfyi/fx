# FX - Micro CSS Framework

Size - 2KB compressed

![Code Language](https://img.shields.io/github/languages/top/phpfyi/fx)
![Code Size](https://img.shields.io/github/languages/code-size/phpfyi/fx)
![Commit Activity](https://img.shields.io/github/commit-activity/m/phpfyi/fx)
![Latest Commit](https://img.shields.io/github/last-commit/phpfyi/fx)

## CSS Reset

The FX framework contains sensible resets for common elements such as form elements.

## CSS Classes

### Breakpoints

The default breakpoint config is as follows and is appended to certain CSS classes to make them responsive.

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
Defaults to 12 columns allowing 1 - 12 classes. Set the $columns config to override.
Columns should be inside an element with a container class (or another flex element)

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

```css
.mar-5 /* used to add 5px margin around elements */
.mar-10 /* used to add 10px margin around elements */
... up to 50 in multiples of 5

.mar-h-5 /* used to add 5px margin left and right around elements */
.mar-h-10 /* used to add 10px margin left and right around elements */
... up to 50 in multiples of 5

.mar-v-5 /* used to add 5px margin top and bottom around elements */
.mar-v-10 /* used to add 10px margin top and bottom around elements */
... up to 50 in multiples of 5

.mar-none /* remove all margins around an element */
```

## Padding

Used to add / remove padding around elements.

```css
.pad-5 /* used to add 5px padding around elements */
.pad-10 /* used to add 10px padding around elements */
... up to 50 in multiples of 5

.pad-h-5 /* used to add 5px padding left and right around elements */
.pad-h-10 /* used to add 10px padding left and right around elements */
... up to 50 in multiples of 5

.pad-v-5 /* used to add 5px padding top and bottom around elements */
.pad-v-10 /* used to add 10px padding top and bottom around elements */
... up to 50 in multiples of 5

.pad-none /* remove all padding around an element */
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

## Vetical Height

Used to define the vertical height on an element.

```css
.vh-10 /* 10% height */
.vh-20 /* 20% height */
... up to 100 in multiples of 10
```