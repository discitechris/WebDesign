---
description: Step-by-step process for Configuring Webpack to support CSS in JS
---

# CSS Configuration

## CSS Development Build

we need to install the loaders:

* **`css-loader`** for loading CSS files with **`import`**
* **`style-loader`** for loading the stylesheet in the DOM

Install the loaders:

```bash
$ npm i css-loader style-loader --save-dev
```

Then configure them in **`webpack.config.js`**:

```javascript
const HtmlWebpackPlugin = require("html-webpack-plugin");
const path = require("path");

module.exports = {
  module: {
    rules: [
      {
        test: /\.css$/,
        use: ["style-loader", "css-loader"]
      }
    ]
  },
  //
};
```

To test CSS in webpack create a simple stylesheet in **`src/style.css`**:

```text
h1 {
    color: orange;
}
```

Also, add an HTML element to our HTML template in **`src/index.html`**:

```text
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Webpack tutorial</title>
</head>
<body>
<h1>Hello webpack!</h1>
</body>
</html>
```

Finally, load the CSS in **`src/index.js`**:

```text
import "./style.css";
console.log("Hello webpack!");
```

## CSS Production Build

### Mini CSS Extract Plugin

{% hint style="info" %}
**NOTE: For Production build**.

 Once CSS loaders are in place you can extract CSS files with [MiniCssExtractPlugin](https://webpack.js.org/plugins/mini-css-extract-plugin/). [👉 ](https://www.npmjs.com/package/mini-css-extract-plugin)
{% endhint %}

we need to install the loaders:

* **`css-loader`** for loading CSS files with **`import`**
* **`minicssextractplugin.loader`**  for extracting CSS into separate files. 
  * It creates a CSS file per JS file which contains CSS.
  * It supports On-Demand-Loading of CSS and SourceMaps.

Install the loaders:

```bash
$ npm install --save-dev mini-css-extract-plugin
```

Then configure them in **`webpack.config.js`**:

```javascript
const MiniCssExtractPlugin = require('mini-css-extract-plugin');
 
module.exports = {
  module: {
    rules: [
      {
        test: /\.css$/i,
        use: [MiniCssExtractPlugin.loader, 'css-loader'],
      },
    ],
  },
  plugins: [new MiniCssExtractPlugin()],
};
```

To test CSS in webpack create a simple stylesheet in **`src/style.css`**:

```text
h1 {
    color: orange;
}
```

Finally, load the CSS in **`src/index.js`**:

```text
import "./style.css";
console.log("Hello webpack!");
```

