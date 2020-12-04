---
description: Step-by-step process for Configuring Webpack to support SASS in JS
---

# SASS Configuration

## SASS Development Build

we need to install the loaders \(and the sass package for Node.js\):

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

