# Natours

A stylish webpage modelled after an app for discovering nature tours. Features advanced CSS techniques such as animations, pseudo-classes, clip-paths, SASS mixins and variables, and more! Demonstrates the use of the block-element-modifier naming convention in HTML markup. Also demonstrates the structure of modern SASS architecture.

Part of the "Advanced CSS and Sass: Flexbox, Grid, Animations and More!" course by
Jonas Schmedtmann (link below).

## Usage

1.  Open index.html in browser

## Technologies

1.  HTML5, CSS3

## Developer Tools

1.  Make sure to type in npm run compile:sass when editing SASS files.
2.  Auto-reload pages by using "live-server"

## Installing SASS for the first time

1. Install node-sass

   ```
   npm install node-sass --save-dev
   ```

2. Update package.json with script:

   ```
   "scripts": {
     "compile:sass": "node-sass sass/main.scss css/style.css -w"
   },
   ```

3. Run script using:

   ```
   npm run compile:sass
   ```

4. Listen for changes using live-server:

   ```
   npm install live-server -g
   live-server
   ```

5. OPTIONAL: Combine dev scripts into one as follows: (make sure to install npm-run-all package, as demonstrated below)

   ```
   "watch:sass": "node-sass sass/main.scss css/style.css -w",
   "devserver": "live-server",
   "start": "npm-run-all --parallel devserver watch:sass",
   ```

## Creating a Build Script

This build script is for compiling SASS, concatenating CSS files, prefixing, and compressing

1. Create the following task in package.json:

   ```
   "compile:sass": "node-sass sass/main.scss css/style.comp.css",
   ```

2. Install npm packages:

   ```
   npm install concat --save-dev
   npm install autoprefixer --save-dev
   npm install postcss-cli --save-dev
   npm install npm-run-all -save-dev
   ```

3. and add the following scripts:

   ```
   "compile:sass": "node-sass sass/main.scss css/style.comp.css",
   "concat:css": "concat -o css/style.concat.css css/icon-font.css css/style.comp.css",
   "prefix:css": "postcss --use autoprefixer -b 'last 10 versions' css/style.concat.css -o css/style.prefix.css",
   "compress:css": "node-sass css/style.prefix.css css/style.css --output-style compressed",
   "build:css": "npm-run-all compile:sass concat:css prefix:css compress:css"
   ```

## Link

- [Advanced CSS and Sass: Flexbox, Grid, Animations and More!](https://www.udemy.com/advanced-css-and-sass/)
