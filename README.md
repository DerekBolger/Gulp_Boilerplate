
A boilerplate for building web projects with [Gulp](https://gulpjs.com/). Uses Gulp 4.x. Bootstrap 4 included.

**Features**

- Concatenate, minify, and lint JavaScript.
- Compile, minify, autoprefix, and lint Sass.
- Optimize SVGs.
- Copy static files and folders into your `dist` directory.
- Watch for file changes, and automatically recompile build and reload webpages.

This Gulp Boilerplate makes it easy to turn features on and off**, so you can reuse it for all projects without having to delete or modify tasks.


## Getting Started

### Dependencies

*__Note:__ if you've previously installed Gulp globally, run `npm rm --global gulp` to remove it. [Details here.](https://medium.com/gulpjs/gulp-sips-command-line-interface-e53411d4467)*

If you have no previous Node or Gulp packages installed make sure these are installed first.

- [Node.js](http://nodejs.org)
- [Gulp Command Line Utility](http://gulpjs.com) `npm install --global gulp-cli`

### Quick Start

1. In bash/terminal/command line, `cd` into your project directory.
2. Run `npm install` to install required files and dependencies.
3. When it's done installing, run one of the task runners to get going:
	- `gulp` manually compiles files.
	- `gulp watch` automatically compiles files and applies changes using [BrowserSync](https://browsersync.io/) when you make changes to your source files.

**Try it out.** After installing, run `gulp` to compile some test files into the `dist` directory. Or, run `gulp watch` and make some changes to see them recompile automatically and auto refresh the browser.



## Documentation

Add source files to the appropriate `src` subdirectories. Gulp will process and and compile them into `dist`.

- JavaScript files in the `src/js` directory will be compiled to `dist/js`. Files in subdirectories under the `js` folder will be concatenated. For example, files in `js/bootstrap` will compile into `bootstrap.js`.
- Files in the `src/sass` directory will be compiled to `dist/css`.
- SVG files placed in the `src/svg` directory will be optimized with SVGO and compiled into `dist/svg`.
- Files and folders placed in the `copy` directory will be copied as-is into the `dist` directory.

### package.json

The `package.json` file holds all of the details about the project.


*__Note:__ `devDependencies` are the dependencies Gulp uses. Don't change these or it will break things.*

### JavaScript

Put your JavaScript files in the `src/js` directory.

Files placed directly in the `js` folder will compile directly to `dist/js` as both minified and unminified files. Files placed in subdirectories under `src/js` will also be concatenated into a single file. For example, all files in `js/bootstrap` or a created folder `js/vendor` will compile into `bootstrap.js` or `js/vendor` for example.

### Sass

Put your [Sass](https://sass-lang.com/) files in the `src/sass` directory.

Gulp generates minified and unminified CSS files. It also includes [autoprefixer](https://github.com/postcss/autoprefixer), which adds vendor prefixes for you.

### SVGs

Place SVG files in the `src/svg` directory.

SVG files will be optimized with [SVGO](https://github.com/svg/svgo) and compiled into `dist/svg`.

### Copy Files

Files and folders placed in the `src/copy` directory will be copied as-is into `dist`.

This is a great place to put HTML files, images, and pre-compiled assets.



# Options & Settings

Gulp Boilerplate makes it easy to customize for projects without having to delete or modify tasks.

Options and settings are located at the top of the `gulpfile.js`.

### Settings

Set features under the `settings` variable to `true` to turn them on (default), and `false` to turn them off.

```js
/**
 * Settings
 * Turn on/off build features
 */

var settings = {
	clean: true,
	scripts: true,
	styles: true,
	svgs: true,
	copy: true,
	reload: true
};
```

### Paths

Adjust the `input` and `output` paths for all of the Gulp tasks under the `paths` variable. Paths are relative to the root project folder.

```js
/**
 * Paths to project folders
 */

var paths = {
	input: 'src/',
	output: 'dist/',
	scripts: {
		input: 'src/js/*',
		output: 'dist/js/'
	},
	styles: {
		input: 'src/sass/**/*.{scss,sass}',
		output: 'dist/css/'
	},
	svgs: {
		input: 'src/svg/*.svg',
		output: 'dist/svg/'
	},
	copy: {
		input: 'src/copy/*',
		output: 'dist/'
	},
	reload: './dist/'
};
```
