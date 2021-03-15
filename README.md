# dom-cat

[![npm version](https://badge.fury.io/js/dom-cat.svg)](https://badge.fury.io/js/dom-cat)
[![npm downloads](https://img.shields.io/npm/dt/dom-cat.svg)](https://www.npmjs.com/package/dom-cat)  
[![Build Status](https://travis-ci.org/myTerminal/dom-cat.svg?branch=master)](https://travis-ci.org/myTerminal/dom-cat)
[![Code Climate](https://codeclimate.com/github/myTerminal/dom-cat.png)](https://codeclimate.com/github/myTerminal/dom-cat)
[![js-myterminal-style](https://img.shields.io/badge/code%20style-myterminal-blue.svg)](https://www.npmjs.com/package/eslint-config/myterminal)
[![Coverage Status](https://img.shields.io/coveralls/myTerminal/dom-cat.svg)](https://coveralls.io/r/myTerminal/dom-cat?branch=master)  
[![Dependency Status](https://david-dm.org/myTerminal/dom-cat.svg)](https://david-dm.org/myTerminal/dom-cat)
[![devDependency Status](https://david-dm.org/myTerminal/dom-cat/dev-status.svg)](https://david-dm.org/myTerminal/dom-cat#info=devDependencies)
[![peer Dependency Status](https://david-dm.org/myTerminal/dom-cat/peer-status.svg)](https://david-dm.org/myTerminal/dom-cat#info=peerDependencies)  
[![License](https://img.shields.io/github/license/myTerminal/dom-cat.svg)](https://opensource.org/licenses/MIT)  
[![NPM](https://nodei.co/npm/dom-cat.png?downloads=true&downloadRank=true&stars=true)](https://nodei.co/npm/dom-cat/)

A minimal library to print and log text to DOM elements

## How to Use

### Directly from a web page

One can use *dom-cat* directly from a web-page by attaching the *dom-cat.js* to the DOM.

    <!-- Attaching the dom-cat script -->
    <script type="text/javascript" src="path/to/library/dom-cat.js"></script>

    <!-- Usage -->
    <script type="text/javascript">
        domCat.init();
    </script>

### With [Webpack](https://webpack.js.org), [Browserify](http://browserify.org) or [RequireJS](http://requirejs.org)

Install *dom-cat* from NPM

    npm install dom-cat --save-dev

Consume as an ES6 module

    import * as domCat from 'dom-cat';

or

    import { print, type, untype } from 'dom-cat';

Consume as a CommonJS module

    var domCat = require('dom-cat');

Consume as an AMD

    require(['dom-cat'], function (domCat) {
        // Consume domCat
    }

Note: You may have to use [Babel](https://babeljs.io) for ES6 transpilation.

### Simple usage

1. Import *dom-cat* functions

        import { print, type, unType } from 'dom-cat';

2. Use one of the functions:

You can use `print` to print logs to a DOM element. Scrolling is automatically applied to the element continuously so that the final lines are always visible if at all the logs happen to be larger than the size of the element.

        print(
            document.querySelector('#element'), // The element to print to
            logs, // An array of text to print
            10 // Delay in milliseconds between two prints
        );

You can use `type` and `untype` to print/unprint text to DOM elements such that appear as an animation. You can optionally also supply a callback that is executed when the operation is complete.

        type(
            document.querySelector('#element'), // The element to type text into
            text, // The text to type
            10, // Delay in milliseconds between characters
            () => {} // A callback to run after all supplied text is typed
        );

        untype(
            document.querySelector('#element'), // The element to untype text from
            10, // Delay in milliseconds between character deletions
            () => {} // A callback to run after all text is untyped
        );

## Demo [coming-soon]

You can view a demo [here](https://myterminal.github.io/dom-cat/examples).

## To-do

* Write unit-tests
