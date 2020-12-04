# Npm installations



sass packages

```text
$ npm install sass --save-dev
```

npm script json

```javascript
"scripts": {
  "watch:sass": "sass sassfolder/main.scss css/style.css -w"
  "compile:sass": "sass sass/main.scss css/style.comp.css",
  "concat:css": "concat -o css/style.concat.css css/icon-font.css css/style.comp.css",
  "prefix:css": "postcss --use autoprefixer -b 'last 10 versions' css/style.concat.css -o css/style.prefix.css",
  "compress:css": "sass css/style.prefix.css css/style.css --output-style compressed",
  "build:css": "npm-run-all compile:sass concat:css prefix:css compress:css"
},
```

run script

```text
$ npm run compile:sass
```

if watch:sass says file not found error. 

follow the github issues checkout @marcosbozzani to solve [link here](https://github.com/sass/node-sass/issues/2022)

