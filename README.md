# checkbox
This [Fuse](https://www.fusetools.com/) project is configured with [Gulp](http://gulpjs.com/), [Rollup](http://rollupjs.org/) and [Babel](https://babeljs.io/) into your  workflow, allowing you to use ES2015+ features in your Fuse app.

## Project file structure
The project is structured as follows:

```bash
- /assets
    /fonts
    /images
    /videos
- /pages
- .gitignore
- checkbox.unoproj
- CHECKBOX.ux
- Gulpfile.js
- LICENSE
- package.json
- README.md
```

## Javascript project
```bash
- /js
    /src
    - app.js
    - api.js
```


## Watch and rollup app.js
Run `gulp watch` to watch for changes to files in the `/src` folder.
When a change occurs, rollup and babel will run, and your transpiled, concatenated JS file will end up as `dist/app.js`. This will in turn trigger an update in the Fuse preview simulator if it's running.

The entry point is `dist/app.js`, which means that only this file will be able to export objects to fuse.

## Watch component model files
Use `npm watch` to enable auto compilation of component model files in `/components` to `dist/components`.

## Babel support
The files in `/src` are the source files to be used by the app. The gulp task will compile the `/src` files to ES5 compatible javascript in `/dist` on any modification.

- `gulp` (default) - compile ES6 via Babel
- `gulp watch` - watch `/src` for changes and compile ES6 to ES5 in `/dist`


### Serving data
The `app.js` file exports a `server` variable which references the Object exported by `server.js`.

You can call `server.api.getData()` to return data served to the app:
- local fake/stub data
- remote server data via a socket connection or HTTP request etc.

Hint: Customize the `server.api` Object to best suite your app!

## Create components
To create components for your app use the `component` generator.

`$ slush xfuse:component`

## Install Fuse modules
Use [fusepm](https://github.com/kristianmandrup/fusepm) to install fuse modules (libraries):

```bash
$ fusepm list
$ fusepm install <module>
```

### FontAwesome

See [fuse-fontawesome](https://github.com/danmademe/fuse-fontawesome)

`fusepm install fontawesome`

Then in a UX view:

```
<fa-check Color="#000" />
```

## License

[MIT](LICENSE)
