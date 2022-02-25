# wkhtmltox

This repository contains the [latest stable compiled binaries](https://github.com/wkhtmltopdf/wkhtmltopdf/releases/latest) of wkhtmltopdf from the [wkhtmltopdf project](https://github.com/wkhtmltopdf/wkhtmltopdf).

The binaries are built for Ubuntu 18.04 buster and stretch amd64 architectures are included.

Or sometimes you just want a quick solution for your dev environment ;)

## Installation

This package is published on [Packagist](https://packagist.org/packages/michael-schaefer-eu/wkhtmltox) and should be installed with [Composer](https://getcomposer.org/download/).

The version of the binary is equal to the git tag.
Composer will install the latest version by default.
```bash
$ composer require-dev michael-schaefer-eu/wkhtmltox
```
_Note: you should not use this package (or any other of that kind) in production environments!_


Composer will install the package in your project path into the _vendor/michael-schaefer-eu/wkhtmltox/_ directory.

The binaries are located in the _vendor/michael-schaefer-eu/wkhtmltox/bin/_ directory.

Composer will symlink them to the _vendor/bin/_ directory.


Check the Version:
```bash
$ wkhtmltopdf -V
wkhtmltopdf 0.12.6 (with patched qt)
```

### Usage

With the [KNP-Snappy](https://github.com/KnpLabs/snappy) package, you can now use the binaries to create PDFs from HTML.

You can use the path constants from this project to easily locate the binary paths (with PSR 4 Autoloader):

``` php
<?php
use Knp\Snappy\Pdf;
use Wkhtmltox\Wkhtmltopdf;

$snappyPdf = new Pdf(Wkhtmltopdf::BUSTERAMD64);
``` 

_OR_ If you symlinked the binaries to _/usr/local/bin_:

``` php
<?php
use Knp\Snappy\Pdf;

$snappyPdf = new Pdf('/usr/local/bin/wkhtmltopdf');
```
