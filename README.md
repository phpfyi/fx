# FX

Micro CSS Framework

![Code Language](https://img.shields.io/github/languages/top/phpfyi/fx)
![Code Size](https://img.shields.io/github/languages/code-size/phpfyi/fx)
![Commit Activity](https://img.shields.io/github/commit-activity/m/phpfyi/fx)
![Latest Commit](https://img.shields.io/github/last-commit/phpfyi/fx)

## Breakpoints

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

## Alignment

Align flex and non flex elements.

```css
.align-c /* flex align items to center */
.align-v /* flex align items vertically */
.align-h /* align element horizontally */
.align-h-r /* flex align items horizontally and to the right */
```

## Clear

Used to clear floated elements.

```css
.cl /* clear left */
.cr /* clear right */
.cb /* clear both */
```

## Columns

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

## Container

Container elements can be used to create fixed centered elements with a variable number of child columns.

```css
.container /* full width flex container */
.container-xs /* xs width centered flex container */
.container-m /* m width centered flex container */
...
```
