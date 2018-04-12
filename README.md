# gulp-gtag

> Injects Google Analytics (gtag) code into HTML files.

[![Build Status](http://img.shields.io/travis/hal313/gulp-gtag/master.svg?style=flat-square)](https://travis-ci.org/hal313/gulp-gtag)
[![NPM version](http://img.shields.io/npm/v/gulp-gtag.svg?style=flat-square)](https://www.npmjs.com/package/gulp-gtag)
[![Dependency Status](http://img.shields.io/david/hal313/gulp-gtag.svg?style=flat-square)](https://david-dm.org/hal313/gulp-gtag)

## Information

This is a fork of [gulp-ga](https://github.com/zhhz/gulp-ga) and has been modified to support the newer gtag script
for Google Analytics.

<table>
<tr>
<td>Package</td><td>gulp-gtag</td>
</tr>
<tr>
<td>Description</td>
<td>Injects Google Analytics (gtag) code into HTML with Gulp (gulpjs.com)</td>
</tr>
<tr>
<td>Node Version</td>
<td>>= 0.9</td>
</tr>
<tr>
<td>Gulp Version</td>
<td>3.x</td>
</tr>
</table>

## Usage


#### Install

```bash
$ npm install gulp-gtag --save-dev
```

## Example

```js
var gulp = require('gulp');
var gtag = require('gulp-gtag');

// Basic usage:
gulp.task('gtag', function(){
  gulp.src('./index.html')
  .pipe(gtag({uid: 'UA-12345678-1'}))
  .pipe(gulp.dest('./'));
});

```

## Options

### options.uid
Set the uid (required)

    Type: `String`

Example:

```js
.pipe(gtag({uid: 'UA-12345678-1'}))
```

### options.tag
Set a specific tag to insert before it.

    Type: `String`
    Default: `head`

Example:

```js
.pipe(gtag({tag: 'head'}))
.pipe(gtag({tag: 'body'}))

```

### options.indent
Number of spaces for indentation (for formatting)

    Type: `Number`
    Default: `4`

Example:

```js
.pipe(gtag({indent: 2}))
```

### options.minify
Minify GA script code (remove `\n` and trailing whitespace).

    Type: `Boolean`
    Default: `false`

Example:

```js
.pipe(gtag({minify: true}))
```

### options.nonceTag
Add a nonce attribute and a nonce template to the script tag. So that we can implement a Content Security Policy that does not allow unsafe-inline scripts to be loaded.

    Type: `Boolean`
    Default: `false`

Example:

```js
.pipe(gtag({nonceTag: true}))
```



## LICENSE

[MIT License](https://raw.githubusercontent.com/hal313/gulp-gtag/master/LICENSE)
