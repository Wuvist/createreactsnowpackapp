# App Setup

## React app

`npx create-react-app react-app --template typescript`

* npx: installed 98 in 4.172s
* Done in 13.77s.
* Done in 8.32s.
* Done in 6.60s.

* Total: 4.172 + 13.77 + 8.32 + 6.60 = 32.862

### Misc

* No `git` repo created; but has gitignore.
* **4624** packages including dependency added
  * `yarn list | wc -l`
* Complete docs: https://create-react-app.dev/

### Available commands
* yarn start     Starts the development server.
* yarn build     Bundles the app into static files for production.
* yarn test     Starts the test runner.
* yarn eject  Removes this tool and copies build dependencies

## Snowpack app

`npx create-snowpack-app snowpack-app --template @snowpack/app-template-react-typescript --use-yarn`

* npx: installed 30 in 1.584s

* Total: npx create-snowpack-app snowpack-app --template  --use-yarn  11.92s user 5.86s system 116% cpu 15.202 total

### Available commands

* yarn install     Install your dependencies. (We already ran this one for you!)
* yarn start       Start your development server.
* yarn run build   Build your website for production.
* yarn test        Run your tests.

### Misc

* `git` repo created with gitignore.
* **2426** packages including dependency added
* Complete docs for snowpack: https://www.snowpack.dev/
  * Single line doc for `CSA`: `npx create-snowpack-app new-dir --template @snowpack/app-template-NAME [--use-yarn | --use-pnpm | --no-install]`

# Run App

`yarn start` for both

## React app

Script are bundled:

```html
<script src="/static/js/bundle.js"></script><script src="/static/js/0.chunk.js"></script><script src="/static/js/main.chunk.js"></script>
```

## Snowpack app

Replying on browser's es module support:

```html
<script type="module" src="/_dist_/index.js"></script>
```

# Summary

* Both `CRA` & `CSA` has well maintained project templates
  * IHMO, `CSA` template is slightly better, like separate devDepenency
* Development experiences are similar
  * It's the same TypeScript / React staff behind
    * `App.tsx` & `App.test.tsx` are almost identical
  * Just that wrapped in different convention
    * `CRA` expose whole `tsconfig.json`
    * `CRA` extends `tsconfig.json` from `@snowpack/app-scripts-react/tsconfig.base.json`
* Both support `HMR` - hot module reload, development experience should be quite smooth
  * CRA depends on `webpack-dev-server` https://webpack.js.org/concepts/hot-module-replacement/
  * https://www.snowpack.dev/#hot-module-replacement
* Development speed is similar for hello world app
* Suppose it should change as project become huge:
  * `CRA` does need **packing** whereas `CSA` doesn't
* `CSA` can have `packing`, just add `"plugins": [["@snowpack/plugin-webpack", {/* ... */}]]`
  * https://www.snowpack.dev/#webpack
* Cypress? just `yarn add cypress --dev` for both
