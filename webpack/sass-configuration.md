---
description: Step-by-step process for Configuring Webpack to support SASS in JS
---

# SASS Configuration

## SASS Development Build

we need to install the loaders \(and the **`sass`** package for **Node.js**\):

* **`sass-loader`** for loading SASS files with **`import`**
* **`css-loader`** for loading CSS files as modules
* **`style-loader`** for loading the stylesheet in the DOM

Install the loaders:

```bash
$ npm i css-loader style-loader sass-loader --save-dev
$ # node-sass is deprecated. install sass for sass-loader to work.
$ npm i sass --save-dev
```

 Then configure them in **`webpack.config.js`**:

```javascript
const HtmlWebpackPlugin = require("html-webpack-plugin");
const path = require("path");

module.exports = {
  module: {
    rules: [
      {
        test: /\.scss$/,
        use: ["style-loader", "css-loader", "sass-loader"]
      }
    ]
  },
  //
};
```

 To test SASS in webpack create a simple stylesheet in **`src/style.scss`**:

```css
@import url('https://fonts.googleapis.com/css2?family=Manrope:wght@200;300;400;500;600;700;800&display=swap');

$font: "Manrope", sans-serif;
$primary-color: #13B007;
body { 
        font-family: $font;
        font-weight: 400;
        font-size: 16px;
        line-height: 1.7;
        color: $primary-color;
        }

```

Finally, load the SASS file in **`src/index.js`**:

```javascript
import "./style.scss";
console.log("Hello webpack!");
```

## SASS-CSS Production Build

### Mini CSS Extract Plugin

{% hint style="info" %}
**NOTE: For Production build**.

 Once CSS loaders are in place you can extract CSS files with [MiniCssExtractPlugin](https://webpack.js.org/plugins/mini-css-extract-plugin/). [👉 ](https://www.npmjs.com/package/mini-css-extract-plugin)
{% endhint %}

we need to install the loaders:

* **`sass-loader`** for loading SASS files with **`import`**
* **`css-loader`** for loading CSS files as modules
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
        test: /\.scss$|\.sass$/i,
        use: [MiniCssExtractPlugin.loader, 'css-loader', 'sass-loader'],
      },
    ],
  },
  plugins: [new MiniCssExtractPlugin()],
};
```

To test SASS in webpack create a simple stylesheet in **`src/style.scss`**:

```css
@import url('https://fonts.googleapis.com/css2?family=Manrope:wght@200;300;400;500;600;700;800&display=swap');

$font: "Manrope", sans-serif;
$primary-color: #13B007;
body { 
        font-family: $font;
        font-weight: 400;
        font-size: 16px;
        line-height: 1.7;
        color: $primary-color;
        }

```

Finally, load the SASS file in **`src/index.js`**:

```javascript
import "./style.scss";
console.log("Hello webpack!");
```

