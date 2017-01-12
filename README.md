![backpack](https://cloud.githubusercontent.com/assets/4060187/21872211/318795e8-d835-11e6-8376-bea370605361.png)

<strong>Build better backends with Webpack.</strong>

## How to use

Install it:

```bash
npm i backpack-core --save
```

and add a script to your package.json like this:

```json
{
  "scripts": {
    "dev": "backpack"
  }
}
```

After that there are just a few ~~conventions~~ defaults:

- `src/index.js`: the entry of your app.

...actually thats it.

**Backpack comes with the "battery-pack included":**

- Latest ES6 features (including module syntax, async/await, object rest spread)
- SUPER Friendly, human readable error messages
- Live reload (on saves, add/delete file, etc.)
- Zero-config, one dependency.

HOWEVER, you can configure Backpack to your project's needs. You can modify the underlying Webpack 2 configuration. 

### Custom configuration

For custom advanced behavior, you can create a `backpack.config.js` in the root of your project's directory (next to `package.json`). Note: `backpack.config.js` is a regular Node.js module, not a JSON file. It gets used by the Backpack build phase, but does not itself go through babel transformation. So only use JS that's supported by your current Node.js version.

```js
// backpack.config.js
module.exports = {
  /* config options here */
}
```

### Customizing Webpack

[Example](https://github.com/jaredpalmer/backpack/tree/master/packages/backpack-examples/with-custom-webpack-config)  
To extend webpack, you can define a function that extends its config via `backpack.config.js`.

```js
// backpack.config.js
module.exports = {
  webpack: (config, options) => {
    // Perform customizations to config
    // Important: return the modified config
    return config
  }
}
```


### Building for Production
Add a npm script for the build step:
```json
{
  "scripts": {
    "dev": "backpack",
    "build": "backpack build"
  }
}
```
Then run the build command and start your app
```bash
npm run build
node ./build/server/main.js   
```

## Authors

- Jared Palmer ([@jaredpalmer](https://twitter.com/jaredpalmer)) - The Palmer Group
