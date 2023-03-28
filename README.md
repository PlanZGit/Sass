# Sass Crash Course

https://sass-lang.com/guide

Live Sass Complier Extension.

1. write scss file
2. generate css with sass live
3. link css to html

# Variables

    $primaryBtn: rgb(177, 255, 181);
    $textColor: black;

# Nesting

    header {
      background: aqua;
      display: flex;
      justify-content: center;
      button {
        background: $primaryBtn;
        position: relative;
        &:hover {
          background: red;
        }
        &::after {
          content: "Hello";
          position: absolute;
          top: 0;
          left: 0;
        }
      }
      p {
        color: red;
      }
    }

# Partials and Modules

## Partials

Modularize your CSS <br>
Live Sass Complier Ingores partials

    _header.scss

## Modules

Recommend using @import

    @import "./variables";
    @import "./header";

@use - recommmend reading more on https://sass-lang.com/guide

    @use 'base';

    .inverse {
      background-color: base.$primary-color;
      color: white;
    }

# Mixins

    @mixin flexCenter($dir: row) {
      display: flex;
      flex-direction: $dir;
      justify-content: center;
      align-items: center;
      height: 100vh;
    }

    header {
      @include flexCenter(column);
    }

# Extend/Inheritance

## Extend

    header {
      @include flexCenter(column);

      background: aqua;
      button {
        background: $primaryBtn;
        position: relative;
        &:hover {
          background: red;
        }
        &::after {
          content: "Hello";
          //   position: absolute;
          top: 0;
          left: 0;
        }
      }
      p {
        color: red;
      }
    }

    .contact {
      @extend header;
    }

# Operators

    +, -, *, math.div(), and %
