# dolmetscher

A flexible FREE and UNLIMITED node package to translate between different languages in a simple way using multiple translators.

> **_NOTE:_**  at the moment, only the google translator is supported. However, other translators will be integrated SOON.

## Motivation
There are other libraries that can be used for this task, but let's face it, most of them are buggy, not free, limited, not supported anymore or complex to use.

Therefore, I decided to build this simple tool. It is 100% free, unlimited, easy to use and provide support for all languages.

Basically, my goal was to integrate support for multiple famous translators in this tool.

This package idea is inspired from the python   [**deep_translator**](https://github.com/nidhaloff/deep_translator) package, where multiple translators are integrated in one too.

## Features:
- Support for google translator
- Simple text translation
- Batch translation
- File translation

## Todos
- Add support for other translators (coming soon)

## Installation

```
npm install dolmetscher --save
```

## Usage

#### Imports

```js

const {GoogleTranslator} = require('../dolmetscher');

```

#### Simple Text Translation

```js
/*
- you need to create a GoogleTranslator object.
- the first argument is the target language to translate to
- the second argument is the source language (default to auto)
- provide the text you want to translate as an argument to the translate function

*/
const google = new GoogleTranslator('en', 'auto');

google.translateText("bonjour la vie").then(res => console.log("translatedText: ", res));

```

- Alternatively you can use the async/await syntax:

```js

async function translate() {
    let google = new GoogleTranslator('en', 'auto');

    try {
        const res = await google.translateText("bonjour la vie");
        return res;
    }

    catch(err) {
        console.log("translation error: ", err);
    }
    
}


```

#### Batch Translation

```js

const google = new GoogleTranslator('en', 'auto');
 const texts = ['bonsoir le monde', 'Hallo Welt', 'guten morgen'];

google.translateBatch(texts)
            .then(res => console.log("batch translation: ", res));

```

#### File Translation

```js

const google = new GoogleTranslator('en', 'auto');
const filePath = 'your_file_path.txt';

google.translateFile(f)
            .then(res => console.log("translated file: ", res));

```


## Contributions

Contributions are always welcome. Feel free to make a pull request. I would appreciate it if you star the github repo so that others notice it.

Please feel free to open an issue if you encountered any problems or if you have a new idea or enhancement.