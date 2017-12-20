# Usage

## Development

Sample files are included in `source`. These files are meant to be replaced. The only constraint is that there must be a `source/index.js` file. Place all other files  inside `source` (nested sub-directories allowed).

`npm run start` to start the dev-server and view site at: `http://localhost:8080`. As files are edited in `source` the browser will update.

## Build

`npm run build` to create a production build of the site in `build` directory at project root. This is a static build so it can be opened directly in a browser.

# Notes

## JavaScript, SASS, CSS files

This project uses Webpack which relies on a dependency graph. What this means as far as this project is concerned is that all JavaScript, SASS, and CSS files must be imported in `index.js` (or in files that can be accessed via `index.js`). See the sample included with the project at `source/index.js` for an example of how to do this.

## HTML and images

Nothing special needs to be done to HTML and image files apart from placing them somewhere in `source`.

## Image Compression

The build script losslessly compresses the images. To disable image compression when running `npm run build`, simply remove the `--compress` flag in the `postbuild` script in `package.json`.

## Fonts
To use a font from a CDN (like Google Fonts), place the `<link>` in the `<header>` of each HTML page that requires the font. Local fonts that are included in `source` but are not referenced by a SCSS/CSS/JavaScript file will not be included in the build.

## jQuery
To use jQuery, first install it as a dependency: `npm install --save jquery`. Then include `import $ from 'jquery';` at the top every JavaScript file that uses jQuery.

## Supported Browsers

Use the `browserslist` file to list supported browsers. This affects what vendor prefixes get applied to the CSS, among other things. (See [https://github.com/ai/browserslist](https://github.com/ai/browserslist) for more information on how to use this file).
