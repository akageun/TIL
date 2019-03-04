# es6-study
ES6를 사용하기 위한 프로젝트.

## 개발환경 
```
mkdir es6-study && cd es6-study

npm init -y
```

###### babel
```
npm i -D babel-loader babel-core babel-preset-env
```

###### webpack
```
npm i -D webpack webpack-dev-server webpack-cli
```

###### CSS Module
```
npm i -D style-loader css-loader sass-loader node-sass
```

###### index.html
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <title>ES6 Stduy Project</title>
</head>
<body>
    <h1>ES6 Study Project</h1>
    <script src="/dist/bundle.js"></script>
</body>
</html>
```

###### index.js
```
const tmpValue = "Test Value";
console.log(`this is ${tmpValue}`);
``` 

###### package.json
```json
{
  "name": "es6-study",
  "version": "1.0.0",
  "description": "",
  "main": "index.js",
  "scripts": {
    "build": "webpack",
    "dev": "webpack-dev-server --open --progress"
  },
  "keywords": [],
  "author": "",
  "license": "ISC",
  "devDependencies": {
    "babel-core": "^6.26.3",
    "babel-loader": "^7.1.5",
    "babel-preset-env": "^1.7.0",
    "css-loader": "^2.1.0",
    "node-sass": "^4.11.0",
    "sass-loader": "^7.1.0",
    "style-loader": "^0.23.1",
    "webpack": "^4.29.6",
    "webpack-cli": "^3.2.3",
    "webpack-dev-server": "^3.2.1"
  }
}

```

###### webpack.config.js
```javascript 1.8
const webpack = require('webpack');
const path = require('path');

module.exports = {
    entry: './index.js',
    output: {
        path: path.resolve(__dirname, 'dist'),
        publicPath: '/dist/',
        filename: 'bundle.js'
    },
    module: {
        rules: [
            {
                test: /\.js$/,
                include: path.join(__dirname),
                exclude: /(node_modules)|(dist)/,
                use: {
                    loader: 'babel-loader',
                    options: {
                        presets: ['env']
                    }
                }
            }
        ]
    }
};

```