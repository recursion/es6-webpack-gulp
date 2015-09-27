# es6-webpack-gulp boilerplate
A barebones boilerplate for starting webapps.

## Usage

## Development
To run tests, type `npm test` or `karma start` in the terminal. Read more about testing [below](#testing).

# Getting Started

## File Structure
```
client
⋅⋅app/
⋅⋅⋅⋅app.js * app entry file
⋅⋅⋅⋅modules/ * where modules live
..assets/  * where statics assets go
..index.html
```

## Dependencies
Tools needed to run this app:
* `node` and `npm`
Once you have these, install the following as globals:  
`npm install -g gulp karma karma-cli webpack`

### Gulp Tasks
Here's a list of available tasks:
* `webpack`
  * runs Webpack, which will transpile, concatenate, and compress (collectively, "bundle") all assets and modules into `client/bundle.js`.
* `serve`
  * starts a dev server via `browser-sync`, serving the client folder.
* `watch`
  * listens for file changes, rebuilds with Webpack, then refreshes the browser.
* `default` (which is the default task that runs when typing `gulp` without providing an argument)
	* runs `webpack`, `serve`, and `watch`--in that order.
* `component`
  * scaffolds a new Angular component. [Read below](#generating-components) for usage details.

### Testing
To run the tests, run `npm test` or `karma start`.

`Karma` combined with Webpack runs all files matching `*.spec.js` inside the `app` folder. This allows us to keep test files local to the component--which keeps us in good faith with continuing to build our app modularly. The file `spec.bundle.js` is the bundle file for **all** our spec files that Karma will run.

Be sure to define your `*.spec.js` files within their corresponding component directory. You must name the spec file like so, `[name].spec.js`. If you don't want to use the `.spec.js` suffix, you must change the `regex` in `spec.bundle.js` to look for whatever file(s) you want.
`Mocha` is the testing suite and `Chai` is the assertion library. If you would like to change this, see `karma.conf.js`.

> Boilerplate started from: https://github.com/angular-class/NG6-starter
