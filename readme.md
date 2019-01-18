# Stylesheets

Common stylesheets for the different websites hosted and managed by Mat Janson Blanchet.


## Usage

The stylesheets are not compiled, they are provided as sources for you to import into your own code.

The stylesheets exist both in [LESS](http://lesscss.org/) and [SASS](https://sass-lang.com/) formats, available respectively in `src/less` and `src/sass` directories. You may import the format you need.


### Install

Install the dev dependency:

    npm install --save-dev jansensan-stylesheets@latest


### Fonts

While these styles originally relied on Google Fonts, they now *require* self-hosted fonts.

The rationale behind this choice is that it is best to not allow [GAFA](https://en.wikipedia.org/wiki/Big_Four_tech_companies) to track visitors to websites making use of these libraries.

In order to self-host the fonts, download the following fonts:

- [Poly](https://www.fontsquirrel.com/fonts/poly)
- [Source Code Pro](https://www.fontsquirrel.com/fonts/source-code-pro)

Somewhere in your stylesheets, ensure to declare the following:

    @font-face {
      font-family: 'PolyItalic';
      src: url('path/to/font/Poly-Italic.ttf');
    }

    @font-face {
      font-family: 'SourceCodePro';
      src: url('path/to/font/SourceCodePro-Regular.otf');
    }

Note: the `font-family` value must match exactly what is written above.


### General

In your site's main stylesheet, import the stylesheets at the top:

    @import "path/to/node_modules/jansensan-stylesheets/src/sass/jansensan-stylesheet.scss";


### Variables

In the case of React, Angular, or other apps, some components may depend on the color, fonts, and breakpoints variables provided by this library. In such cases, the components' styles may simply import the variables:

    @import 'path/to/node_modules/jansensan-stylesheets/src/sass/common/variables.scss';

The `variables.less`/`variables.scss` files include the other variables files in the same directories. If you wish to import only the breakpoints, the colors, or the fonts, it is possible to be more granular:

    @import 'path/to/node_modules/jansensan-stylesheets/src/sass/common/breakpoints.scss';
