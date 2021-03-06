Knayi Myanmar Script
====================

[![NPM version][npm-image]][npm-url]
![][travis-url]
[![][david-image]][david-url]
![][dt-url]
![][license-url]

> Standalone Myanmar languages JavaScript library, use to build Myanmar **Unicode** standard easily.

## Node Version
 - Required node version >= 4  
 Note: From version >=2.3.0 build step will only support for node >=6

## Features
 - Detector (Unicode and Zawgyi)
 - Converter (Unicode and Zawgyi)
 - SyallBreak (Unicode and Zawgyi)
 - Spelling Check (Unicode and Zawgyi)

## Installation
Using npm
```bash
npm install knayi-myscript --save
```

Using yran
```bash
yarn add knayi-myscript
```

Using CDN
```html
<script src="https://unpkg.com/knayi-myscript@2.2.0/dist/knayi-myscript.min.js"></script>
```

## API
|Method Name | Arguments | Return | Note |
| --- | --- | --- | --- |
| `fontDetect` | `content: String(require)` | `String` | Font Detector, it will detect unicode/zawgyi of the **content** Text. If nothing is matched or possibility are equal, it will return as 'zawgyi' or specified font type in **defaultFont** params. |
| `fontConvert` | `content: String(require)`,<br>`convertTo: fontName(require)`,<br>`convertFrom: fontName(optional)`| `String` | Converting font to target font type. This method need spelling fix, so it gonna use **spellingFix** in default. **convertFrom** will be detect by **fontDetect** when you don't described.<hr> `fontName` must be one of `unicode` or `zawgyi`. |
| `syllBreak` | `content: String(require)`,<br>`fontType: fontName(optional)`,<br>`breakPoint: String(optional)` | `String` |To make systematic word break of Myanmar text. convertFrom will be detect by fontDetect when you don't described.<hr> `fontName` must be one of `unicode` or `zawgyi`. |
| `spellingFix` | `content: String(require)`,<br>`fontType: fontName(optional)` | `String` | **convertFrom** will be detect by **fontDetect** when you don't described. It fix spelling on Myanmar Text.<hr> `fontName` must be one of `unicode` or `zawgyi`. |

## Usage

```javascript
// ES5 Way
var knayi = require('knayi-myscript')

// ES6 Way
import knayi from 'knayi-myscript'
```

## Example

- **fontDetect(content, [defaultFont])**
```javascript
knayi.fontDetect('မဂၤလာပါ') // zawgyi
knayi.fontDetect('မင်္ဂလာပါ') // unicode
```

- **fontConvert(content, convertTo, [convertFrom])**
```javascript
knayi.fontConvert('မဂၤလာပါ', 'unicode', 'zawgyi') // မင်္ဂလာပါ
knayi.fontConvert('မဂၤလာပါ', 'unicode') // မင်္ဂလာပါ
```

- **syllBreak(content, [fontType] [,breakPoint])**
```javascript
knayi.syllBreak('မင်္ဂလာပါ', null, '$$') // 'မင်္ဂလာ$$ပါ'
```

- **spellingFix(content, [fontType])**  
```javascript
knayi.spellingFix('မင်္ဂလာာပါါ') // 'မင်္ဂလာပါ'
```

## Build

 - Required node >=6  
 - `npm run build`  
 To build production run `webpack -p`  

## License
[MIT](./LICENSE)

[npm-url]: https://npmjs.org/package/knayi-myscript
[npm-image]:https://badge.fury.io/js/knayi-myscript.png
[travis-url]:https://api.travis-ci.org/greenlikeorange/knayi-myscript.svg?branch=master
[david-url]:https://david-dm.org/greenlikeorange/knayi-myscript
[david-image]: https://david-dm.org/greenlikeorange/knayi-myscript.png
[dt-url]:https://img.shields.io/npm/dt/knayi-myscript.svg
[license-url]:https://img.shields.io/npm/l/knayi-myscript.svg
