# Sass Introduction

## SASS \(pre-processer\)

Use scss extension and format & methods below

### nested selector

html elements which are nested can be styled using nested selector

```css
 <!--nested selector-->
 ul {
   color : black;
   li {
     background-color: blue;
   }
 }
```

Accessing nested elements applying psuedoclass.

```css
 .navigation {
   list-style: none;
   li {
     display: inline-block;
     margin-left: 30px;
    &:first-child {
      margin: 0;
      <!--evaluetes to .navigation li:first-child-->
    }
    a {
      text-decoration: none;
      text-transform: uppercase;
      <!--evaluetes to .navigation li a-->
    }
   }
 }
```

multiple psuedoclasses and usage of builtin functions.

```css
 .btn-main {
   &:link {
     background-color: $color-secondary;
   }
   &:hover {
   <!--using built sass functions which evaluetes to its usecase-->
     background-color: darken($color-tertiary, 15%)
   }
 }
```

### reusable variables

Always start with '$' sign. syntax

```css
 $color-primary: #f9ed69;
 nav {
   background-color: $color-primary;
 }
```

