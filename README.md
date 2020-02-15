This is a fork of `file-loader` repo: https://github.com/webpack-contrib/file-loader

Please refer to the source for the full documentation.

This loader introduces an additional option: `keepQueryString`. Other than that, it completely mirrors the behaviour of the original `file-loader`.

## Additional options

### `keepQueryString`

Type: `Boolean`
Default: `false`

Preserve query strings in the resulting file output paths.

**webpack.config.js**

```js
module.exports = {
  module: {
    rules: [
      {
        test: /\.(png|jpe?g|gif)$/i,
        loader: '@imageengine/file-loader',
        options: {
          name: '[path][name].[ext]',
          keepQueryString: false | true,
        },
      },
    ],
  },
};
```

**Example**

`keepQueryString: false` (omitting the option has the same effect)
`sourcePath/to/image.png?q=/width_50/quality_50` becomes `outputPath/to/image.png`

`keepQueryString: true`
`sourcePath/to/image.png?q=/width_50/quality_50` becomes `outputPath/to/image.png?q=/width_50/quality_50`
