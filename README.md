# Blutack

## Description

A simple jQuery plugin for dynamically fixing element positions.

![Blutack](blutack.jpg)

* [Features](#features)
* [Requirements](#requirements)
* [Support](#support)
* [Installation](#installation)
* [Usage](#usage)
    * [Options](#options)
    * [Plugin Methods](#plugin-methods)
* [Tests](#tests)
* [Upcoming Features](#upcoming-features)
* [Other Relevant Documentation](#other-relevant-documentation)
* [License](#license)

## Features

* Requires minimal (or no) defensive CSS to keep targeted or surrounding elements from collapsing or changing size when target element's position becomes fixed.
* Includes options to keep a fixed element within the bounds of a specified parent element
* Initialize with data attributes or JS

## Requirements

* jQuery

## Support

Blutack was developed by Scott Blumenthal (scott.blumenthal@nytimes.com).  It is not being actively developed at the moment.  Please submit a [Github issue](https://github.com/newsdev/blutack/issues/new) to request features or report bugs.

## Installation

Download the [full](https://raw.githubusercontent.com/newsdev/blutack/master/jquery.blutack.js) or [minified](https://raw.githubusercontent.com/newsdev/blutack/master/jquery.blutack.min.js) file.

## Usage

Blutack functions like a standard jQuery plugin.  Initialize Blutack on an element *programmatically* with Javascript:

    $('.any-old-selector').blutack();

or *automatically* by adding the `blutack` class.  Options can be inlined by adding a `data-blutack-options` attribute to the element, with options as key/value pairs separated by a semi-colon:

    <div class="blutack" data-blutack-options="offsetTop:10; freezeWidth: true;">Lorem ipsum...</div>

### Options

<table>
  <thead>
    <tr>
      <th>name</th>
      <th>type</th>
      <th>default</th>
      <th>description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>offsetTop</td>
      <td>integer</td>
      <td>0</td>
      <td>Specifies the padding between the viewport top and the element while it is fixed.</td>
    </tr>
    <tr>
      <td>freezeWidth</td>
      <td>boolean</td>
      <td>false</td>
      <td>Fix the width of an element when it is tacked to the value of its untacked width.  If `false`, element width will be set to 'auto' when tacked.</td>
    </tr>
    <tr>
      <td>keepWithin</td>
      <td>DOM node, jQuery selector, or jQuery-wrapped DOM node</td>
      <td></td>
      <td>Must be a parent of the targeted element.  If defined, the target element will become fixed at the specified `offsetTop`, but only as long as it stays within the boundaries of the `keepWithin` element.</td>
    </tr>
  </tbody>
</table>


### Plugin Methods

#### $(selector).blutack([options])

Apply Blutack to the specified element(s).  Element position will be fixed immediately if page is already scrolled past position fix position.  Returns $(selector).

#### $(selector).blutack('remove')

Instantly unfixes any tacked elements that match **selector** and deactivates blutack behavior on those elements.  Returns $(selector).

#### $(selector).blutack('tacked')

Returns `true` if the element is currently fixed, `false` if element is in its original unfixed position.

#### $(selector).blutack('retack')

Manually retack (and reposition if necessary) all tacked elements matching **selector**.

## Tests

There are no unit tests for Blutack, but a test page showing a variety of behavior does exist at [examples/index.html](examples/index.html).

## Upcoming Features

* Possibly add triggers for `tack` and `untack` events?

## License

The MIT License (MIT)

Copyright (c) 2014 The New York Times Company

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.