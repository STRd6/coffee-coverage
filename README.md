Istanbul and JSCoverage-style instrumentation for CoffeeScript files.

CoffeeCoverage
==============

[![Coverage Status](https://coveralls.io/repos/DanielXMoore/CoffeeCoverage/badge.svg?branch=master)](https://coveralls.io/r/DanielXMoore/CoffeeCoverage?branch=master)

Instruments CoffeeScript files for code coverage.  Compiles .coffee files to .js files, and adds JSCoverage or Istanbul style instrumentation for the original coffee script source.

[![NPM](https://nodei.co/npm/@danielx/coffeecoverage.png?downloads=true&downloadRank=true&stars=true)](https://npmjs.org/package/@danielx/coffeecoverage)

Features
--------

* Native coffeescript instrumentation - [not based on source maps](./docs/comparison-to-ibrik.md)
* Conditional instrumentation with [pragmas](./docs/pragmas.md)
* Support for [nyc](./docs/HOWTO-nyc.md) style instrumentation
* Support for [Istanbul](./docs/HOWTO-istanbul.md) style instrumentation
* Support for [JSCoverage](./docs/HOWTO-jscoverage.md) style instrumentation
* Support for [Streamline compiler](./docs/streamline.md) style instrumentation
* Dynamic instrumentation - instrument your code at run time
* [Precompiled instrumentation](./docs/cli.md)

Quick Start
-----------

Assuming you have a folder named "test" full of mocha tests, which directly loads your .coffee
files, then from your project's folder, run:

```bash
npm install --save-dev @danielx/coffeecoverage
npm install --save-dev istanbul
mocha --recursive --compilers coffee:coffeescript/register --require @danielx/coffeecoverage/register-istanbul test

./node_modules/.bin/istanbul report
```

You should now have an Istanbul coverage report in ./coverage/lcov-report/index.html.

If this doesn't quite do what you're after, check out our tutorials below:

Tutorials:
----------

* [Mocha and Istanbul Guide](./docs/HOWTO-istanbul.md)
* [Mocha and JSCoverage Guide](./docs/HOWTO-jscoverage.md)
* [Istanbul and Tape Guide](./docs/HOWTO-tape-not-mocha.md) courtesy [@jessaustin](https://github.com/jessaustin).
* [Codeship and Coveralls](./docs/HOWTO-codeship-and-coveralls.md)
* [Travis-CI and Coveralls](./docs/HOWTO-travisci-and-coveralls.md)
* [Ignoring code with Pragmas](./docs/pragmas.md)

Have CoffeeCoverage working in a setup not described above?
[Raise an issue](https://github.com/DanielXMoore/CoffeeCoverage/issues/new) and let us know how you're
using CoffeeCoverage, so we can document it here.

What it Does
------------

CoffeeCoverage is a tool for determining the coverage of your unit tests.  It does this
by instrumenting .coffee files to see how often each line, branch, or function is executed.
CoffeeCoverage is capable of producing both [Istanbul](./docs/HOWTO-istanbul.md) and
[JSCoverage](./docs/HOWTO-jscoverage.md) style instrumentation.
