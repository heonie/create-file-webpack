# Create file plugin for WebPack
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)

Forked from https://github.com/Appius/create-file-webpack and modified.

Very simple plugin to create a file at the end of the build process with the particular text.

## Installation
```
npm i create-file-webpack --save-dev
```

## Usage
```js
const CreateFileWebpack = require('create-file-webpack')

// webpack config
{
  plugins: [
    new CreateFileWebpack({options})
  ]
}
```

## List of possible options:

````js
const path = require('path');
const fs = require('fs');

var opts = {
    // path to folder in which the file will be created
    path: './dist',
    // file name
    fileName: 'generated.xml',
    // content of the file
    content: fs.readFileSync(path.join(__dirname, 'public/source.xml')),
    // Data for interpolation of the content. See https://lodash.com/docs/4.17.15#template
    templateData: JSON.parse(fs.readFileSync(path.join(__dirname, 'package.json')))
};
````
