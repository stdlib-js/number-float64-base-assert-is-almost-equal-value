<!--

@license Apache-2.0

Copyright (c) 2025 The Stdlib Authors.

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

   http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.

-->


<details>
  <summary>
    About stdlib...
  </summary>
  <p>We believe in a future in which the web is a preferred environment for numerical computation. To help realize this future, we've built stdlib. stdlib is a standard library, with an emphasis on numerical and scientific computation, written in JavaScript (and C) for execution in browsers and in Node.js.</p>
  <p>The library is fully decomposable, being architected in such a way that you can swap out and mix and match APIs and functionality to cater to your exact preferences and use cases.</p>
  <p>When you use stdlib, you can be absolutely certain that you are using the most thorough, rigorous, well-written, studied, documented, tested, measured, and high-quality code out there.</p>
  <p>To join us in bringing numerical computing to the web, get started by checking us out on <a href="https://github.com/stdlib-js/stdlib">GitHub</a>, and please consider <a href="https://opencollective.com/stdlib">financially supporting stdlib</a>. We greatly appreciate your continued support!</p>
</details>

# isAlmostEqualValue

[![NPM version][npm-image]][npm-url] [![Build Status][test-image]][test-url] [![Coverage Status][coverage-image]][coverage-url] <!-- [![dependencies][dependencies-image]][dependencies-url] -->

> Test if two double-precision floating-point numbers are approximately equal within a specified number of ULPs (units in the last place).

<section class="installation">

## Installation

```bash
npm install @stdlib/number-float64-base-assert-is-almost-equal-value
```

Alternatively,

-   To load the package in a website via a `script` tag without installation and bundlers, use the [ES Module][es-module] available on the [`esm`][esm-url] branch (see [README][esm-readme]).
-   If you are using Deno, visit the [`deno`][deno-url] branch (see [README][deno-readme] for usage intructions).
-   For use in Observable, or in browser/node environments, use the [Universal Module Definition (UMD)][umd] build available on the [`umd`][umd-url] branch (see [README][umd-readme]).

The [branches.md][branches-url] file summarizes the available branches and displays a diagram illustrating their relationships.

To view installation and usage instructions specific to each branch build, be sure to explicitly navigate to the respective README files on each branch, as linked to above.

</section>

<section class="usage">

## Usage

```javascript
var isAlmostEqualValue = require( '@stdlib/number-float64-base-assert-is-almost-equal-value' );
```

#### isAlmostEqualValue( a, b, maxULP )

Tests if two double-precision floating-point numbers are approximately equal within a specified number of ULPs (units in the last place).

```javascript
var EPS = require( '@stdlib/constants-float64-eps' );

var bool = isAlmostEqualValue( 1.0, 1.0+EPS, 1 );
// returns true

bool = isAlmostEqualValue( 1.0, 1.0+EPS, 0 );
// returns false
```

The function returns `false` if either input value is `NaN`.

```javascript
var bool = isAlmostEqualValue( NaN, 1.0, 1 );
// returns false

bool = isAlmostEqualValue( 1.0, NaN, 1 );
// returns false

bool = isAlmostEqualValue( NaN, NaN, 1 );
// returns false
```

The function does not distinguish between `-0` and `+0`, treating them as equal.

```javascript
var bool = isAlmostEqualValue( 0.0, -0.0, 0 );
// returns true
```

</section>

<!-- /.usage -->

<section class="notes">

</section>

<!-- /.notes -->

<section class="examples">

## Examples

<!-- eslint no-undef: "error" -->

```javascript
var EPS = require( '@stdlib/constants-float64-eps' );
var isAlmostEqualValue = require( '@stdlib/number-float64-base-assert-is-almost-equal-value' );

var bool = isAlmostEqualValue( 1.0, 1.0+EPS, 1 );
console.log( bool );
// => true

bool = isAlmostEqualValue( 1.0+EPS, 1.0, 1 );
console.log( bool );
// => true

bool = isAlmostEqualValue( 1.0, 1.0+EPS+EPS, 1 );
console.log( bool );
// => false

bool = isAlmostEqualValue( 1.0, 1.0+EPS, 0 );
console.log( bool );
// => false

bool = isAlmostEqualValue( -0.0, 0.0, 0 );
console.log( bool );
// => true

bool = isAlmostEqualValue( 1.0, NaN, 1 );
console.log( bool );
// => false

bool = isAlmostEqualValue( NaN, NaN, 1 );
console.log( bool );
// => false
```

</section>

<!-- /.examples -->

<!-- Section for related `stdlib` packages. Do not manually edit this section, as it is automatically populated. -->

<section class="related">

</section>

<!-- /.related -->

<!-- Section for all links. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->


<section class="main-repo" >

* * *

## Notice

This package is part of [stdlib][stdlib], a standard library for JavaScript and Node.js, with an emphasis on numerical and scientific computing. The library provides a collection of robust, high performance libraries for mathematics, statistics, streams, utilities, and more.

For more information on the project, filing bug reports and feature requests, and guidance on how to develop [stdlib][stdlib], see the main project [repository][stdlib].

#### Community

[![Chat][chat-image]][chat-url]

---

## License

See [LICENSE][stdlib-license].


## Copyright

Copyright &copy; 2016-2025. The Stdlib [Authors][stdlib-authors].

</section>

<!-- /.stdlib -->

<!-- Section for all links. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->

<section class="links">

[npm-image]: http://img.shields.io/npm/v/@stdlib/number-float64-base-assert-is-almost-equal-value.svg
[npm-url]: https://npmjs.org/package/@stdlib/number-float64-base-assert-is-almost-equal-value

[test-image]: https://github.com/stdlib-js/number-float64-base-assert-is-almost-equal-value/actions/workflows/test.yml/badge.svg?branch=main
[test-url]: https://github.com/stdlib-js/number-float64-base-assert-is-almost-equal-value/actions/workflows/test.yml?query=branch:main

[coverage-image]: https://img.shields.io/codecov/c/github/stdlib-js/number-float64-base-assert-is-almost-equal-value/main.svg
[coverage-url]: https://codecov.io/github/stdlib-js/number-float64-base-assert-is-almost-equal-value?branch=main

<!--

[dependencies-image]: https://img.shields.io/david/stdlib-js/number-float64-base-assert-is-almost-equal-value.svg
[dependencies-url]: https://david-dm.org/stdlib-js/number-float64-base-assert-is-almost-equal-value/main

-->

[chat-image]: https://img.shields.io/gitter/room/stdlib-js/stdlib.svg
[chat-url]: https://app.gitter.im/#/room/#stdlib-js_stdlib:gitter.im

[stdlib]: https://github.com/stdlib-js/stdlib

[stdlib-authors]: https://github.com/stdlib-js/stdlib/graphs/contributors

[umd]: https://github.com/umdjs/umd
[es-module]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Modules

[deno-url]: https://github.com/stdlib-js/number-float64-base-assert-is-almost-equal-value/tree/deno
[deno-readme]: https://github.com/stdlib-js/number-float64-base-assert-is-almost-equal-value/blob/deno/README.md
[umd-url]: https://github.com/stdlib-js/number-float64-base-assert-is-almost-equal-value/tree/umd
[umd-readme]: https://github.com/stdlib-js/number-float64-base-assert-is-almost-equal-value/blob/umd/README.md
[esm-url]: https://github.com/stdlib-js/number-float64-base-assert-is-almost-equal-value/tree/esm
[esm-readme]: https://github.com/stdlib-js/number-float64-base-assert-is-almost-equal-value/blob/esm/README.md
[branches-url]: https://github.com/stdlib-js/number-float64-base-assert-is-almost-equal-value/blob/main/branches.md

[stdlib-license]: https://raw.githubusercontent.com/stdlib-js/number-float64-base-assert-is-almost-equal-value/main/LICENSE

</section>

<!-- /.links -->
