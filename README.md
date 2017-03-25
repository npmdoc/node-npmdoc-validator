# api documentation for  [validator (v7.0.0)](http://github.com/chriso/validator.js)  [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-validator.svg)](https://travis-ci.org/npmdoc/node-npmdoc-validator)
#### String validation and sanitization

[![NPM](https://nodei.co/npm/validator.png?downloads=true)](https://www.npmjs.com/package/validator)

[![apidoc](https://npmdoc.github.io/node-npmdoc-validator/build/screen-capture.buildNpmdoc.browser._2Fhome_2Ftravis_2Fbuild_2Fnpmdoc_2Fnode-npmdoc-validator_2Ftmp_2Fbuild_2Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-validator/build..beta..travis-ci.org/apidoc.html)

![package-listing](https://npmdoc.github.io/node-npmdoc-validator/build/screen-capture.npmPackageListing.svg)



# package.json

```json

{
    "author": {
        "name": "Chris O'Hara",
        "email": "cohara87@gmail.com"
    },
    "bugs": {
        "url": "http://github.com/chriso/validator.js/issues"
    },
    "dependencies": {},
    "description": "String validation and sanitization",
    "devDependencies": {
        "babel-cli": "^6.16.0",
        "babel-plugin-add-module-exports": "^0.2.1",
        "babel-preset-es2015": "^6.16.0",
        "babel-preset-es2015-rollup": "^1.2.0",
        "coveralls": "^2.11.9",
        "eslint": "^3.8.1",
        "eslint-config-airbnb-base": "^9.0.0",
        "eslint-plugin-import": "^2.0.1",
        "istanbul": "^0.4.3",
        "mocha": "^3.1.2",
        "rollup": "^0.29.1",
        "rollup-plugin-babel": "^2.5.1",
        "uglify-js": "^2.6.2"
    },
    "directories": {},
    "dist": {
        "shasum": "c74deb8063512fac35547938e6f0b1504a282fd2",
        "tarball": "https://registry.npmjs.org/validator/-/validator-7.0.0.tgz"
    },
    "engines": {
        "node": ">= 0.10"
    },
    "files": [
        "index.js",
        "lib",
        "README.md",
        "LICENCE",
        "validator.js",
        "validator.min.js"
    ],
    "gitHead": "c812c206fe0004ea81e4ed854faf2a526bfa8e30",
    "homepage": "http://github.com/chriso/validator.js",
    "keywords": [
        "validator",
        "validation",
        "validate",
        "sanitization",
        "sanitize",
        "sanitisation",
        "sanitise",
        "assert"
    ],
    "license": "MIT",
    "main": "index.js",
    "maintainers": [
        {
            "name": "cohara87",
            "email": "cohara87@gmail.com"
        }
    ],
    "name": "validator",
    "optionalDependencies": {},
    "readme": "ERROR: No README data found!",
    "repository": {
        "type": "git",
        "url": "git+ssh://git@github.com/chriso/validator.js.git"
    },
    "scripts": {
        "build": "npm run build:browser && npm run build:node",
        "build:browser": "babel-node build-browser && npm run minify",
        "build:node": "babel src -d . --presets es2015 --plugins add-module-exports",
        "clean": "npm run clean:node && npm run clean:browser",
        "clean:browser": "rm -rf validator*.js",
        "clean:node": "rm -rf index.js lib",
        "coveralls": "istanbul cover _mocha --report lcovonly -x validator.js -- -R spec && cat ./coverage/lcov.info | coveralls && rm -rf ./coverage",
        "lint": "eslint src test",
        "minify": "uglifyjs validator.js -o validator.min.js  --compress --mangle --comments '/Copyright/'",
        "pretest": "npm run lint && npm run build",
        "test": "mocha --reporter spec"
    },
    "version": "7.0.0"
}
```



# <a name="apidoc.tableOfContents"></a>[table of contents](#apidoc.tableOfContents)

#### [module validator](#apidoc.module.validator)
1.  [function <span class="apidocSignatureSpan">validator.</span>blacklist (str, chars)](#apidoc.element.validator.blacklist)
1.  [function <span class="apidocSignatureSpan">validator.</span>contains (str, elem)](#apidoc.element.validator.contains)
1.  [function <span class="apidocSignatureSpan">validator.</span>equals (str, comparison)](#apidoc.element.validator.equals)
1.  [function <span class="apidocSignatureSpan">validator.</span>escape (str)](#apidoc.element.validator.escape)
1.  [function <span class="apidocSignatureSpan">validator.</span>isAfter (str)](#apidoc.element.validator.isAfter)
1.  [function <span class="apidocSignatureSpan">validator.</span>isAlpha (str)](#apidoc.element.validator.isAlpha)
1.  [function <span class="apidocSignatureSpan">validator.</span>isAlphanumeric (str)](#apidoc.element.validator.isAlphanumeric)
1.  [function <span class="apidocSignatureSpan">validator.</span>isAscii (str)](#apidoc.element.validator.isAscii)
1.  [function <span class="apidocSignatureSpan">validator.</span>isBase64 (str)](#apidoc.element.validator.isBase64)
1.  [function <span class="apidocSignatureSpan">validator.</span>isBefore (str)](#apidoc.element.validator.isBefore)
1.  [function <span class="apidocSignatureSpan">validator.</span>isBoolean (str)](#apidoc.element.validator.isBoolean)
1.  [function <span class="apidocSignatureSpan">validator.</span>isByteLength (str, options)](#apidoc.element.validator.isByteLength)
1.  [function <span class="apidocSignatureSpan">validator.</span>isCreditCard (str)](#apidoc.element.validator.isCreditCard)
1.  [function <span class="apidocSignatureSpan">validator.</span>isCurrency (str, options)](#apidoc.element.validator.isCurrency)
1.  [function <span class="apidocSignatureSpan">validator.</span>isDataURI (str)](#apidoc.element.validator.isDataURI)
1.  [function <span class="apidocSignatureSpan">validator.</span>isDecimal (str)](#apidoc.element.validator.isDecimal)
1.  [function <span class="apidocSignatureSpan">validator.</span>isDivisibleBy (str, num)](#apidoc.element.validator.isDivisibleBy)
1.  [function <span class="apidocSignatureSpan">validator.</span>isEmail (str, options)](#apidoc.element.validator.isEmail)
1.  [function <span class="apidocSignatureSpan">validator.</span>isEmpty (str)](#apidoc.element.validator.isEmpty)
1.  [function <span class="apidocSignatureSpan">validator.</span>isFQDN (str, options)](#apidoc.element.validator.isFQDN)
1.  [function <span class="apidocSignatureSpan">validator.</span>isFloat (str, options)](#apidoc.element.validator.isFloat)
1.  [function <span class="apidocSignatureSpan">validator.</span>isFullWidth (str)](#apidoc.element.validator.isFullWidth)
1.  [function <span class="apidocSignatureSpan">validator.</span>isHalfWidth (str)](#apidoc.element.validator.isHalfWidth)
1.  [function <span class="apidocSignatureSpan">validator.</span>isHexColor (str)](#apidoc.element.validator.isHexColor)
1.  [function <span class="apidocSignatureSpan">validator.</span>isHexadecimal (str)](#apidoc.element.validator.isHexadecimal)
1.  [function <span class="apidocSignatureSpan">validator.</span>isIP (str)](#apidoc.element.validator.isIP)
1.  [function <span class="apidocSignatureSpan">validator.</span>isISBN (str)](#apidoc.element.validator.isISBN)
1.  [function <span class="apidocSignatureSpan">validator.</span>isISIN (str)](#apidoc.element.validator.isISIN)
1.  [function <span class="apidocSignatureSpan">validator.</span>isISO8601 (str)](#apidoc.element.validator.isISO8601)
1.  [function <span class="apidocSignatureSpan">validator.</span>isISSN (str)](#apidoc.element.validator.isISSN)
1.  [function <span class="apidocSignatureSpan">validator.</span>isIn (str, options)](#apidoc.element.validator.isIn)
1.  [function <span class="apidocSignatureSpan">validator.</span>isInt (str, options)](#apidoc.element.validator.isInt)
1.  [function <span class="apidocSignatureSpan">validator.</span>isJSON (str)](#apidoc.element.validator.isJSON)
1.  [function <span class="apidocSignatureSpan">validator.</span>isLength (str, options)](#apidoc.element.validator.isLength)
1.  [function <span class="apidocSignatureSpan">validator.</span>isLowercase (str)](#apidoc.element.validator.isLowercase)
1.  [function <span class="apidocSignatureSpan">validator.</span>isMACAddress (str)](#apidoc.element.validator.isMACAddress)
1.  [function <span class="apidocSignatureSpan">validator.</span>isMD5 (str)](#apidoc.element.validator.isMD5)
1.  [function <span class="apidocSignatureSpan">validator.</span>isMobilePhone (str, locale)](#apidoc.element.validator.isMobilePhone)
1.  [function <span class="apidocSignatureSpan">validator.</span>isMongoId (str)](#apidoc.element.validator.isMongoId)
1.  [function <span class="apidocSignatureSpan">validator.</span>isMultibyte (str)](#apidoc.element.validator.isMultibyte)
1.  [function <span class="apidocSignatureSpan">validator.</span>isNumeric (str)](#apidoc.element.validator.isNumeric)
1.  [function <span class="apidocSignatureSpan">validator.</span>isSurrogatePair (str)](#apidoc.element.validator.isSurrogatePair)
1.  [function <span class="apidocSignatureSpan">validator.</span>isURL (url, options)](#apidoc.element.validator.isURL)
1.  [function <span class="apidocSignatureSpan">validator.</span>isUUID (str)](#apidoc.element.validator.isUUID)
1.  [function <span class="apidocSignatureSpan">validator.</span>isUppercase (str)](#apidoc.element.validator.isUppercase)
1.  [function <span class="apidocSignatureSpan">validator.</span>isVariableWidth (str)](#apidoc.element.validator.isVariableWidth)
1.  [function <span class="apidocSignatureSpan">validator.</span>isWhitelisted (str, chars)](#apidoc.element.validator.isWhitelisted)
1.  [function <span class="apidocSignatureSpan">validator.</span>ltrim (str, chars)](#apidoc.element.validator.ltrim)
1.  [function <span class="apidocSignatureSpan">validator.</span>matches (str, pattern, modifiers)](#apidoc.element.validator.matches)
1.  [function <span class="apidocSignatureSpan">validator.</span>normalizeEmail (email, options)](#apidoc.element.validator.normalizeEmail)
1.  [function <span class="apidocSignatureSpan">validator.</span>rtrim (str, chars)](#apidoc.element.validator.rtrim)
1.  [function <span class="apidocSignatureSpan">validator.</span>stripLow (str, keep_new_lines)](#apidoc.element.validator.stripLow)
1.  [function <span class="apidocSignatureSpan">validator.</span>toBoolean (str, strict)](#apidoc.element.validator.toBoolean)
1.  [function <span class="apidocSignatureSpan">validator.</span>toDate (date)](#apidoc.element.validator.toDate)
1.  [function <span class="apidocSignatureSpan">validator.</span>toFloat (str)](#apidoc.element.validator.toFloat)
1.  [function <span class="apidocSignatureSpan">validator.</span>toInt (str, radix)](#apidoc.element.validator.toInt)
1.  [function <span class="apidocSignatureSpan">validator.</span>trim (str, chars)](#apidoc.element.validator.trim)
1.  [function <span class="apidocSignatureSpan">validator.</span>unescape (str)](#apidoc.element.validator.unescape)
1.  [function <span class="apidocSignatureSpan">validator.</span>whitelist (str, chars)](#apidoc.element.validator.whitelist)
1.  string <span class="apidocSignatureSpan">validator.</span>version

#### [module validator.isFullWidth](#apidoc.module.validator.isFullWidth)
1.  [function <span class="apidocSignatureSpan">validator.isFullWidth.</span>default (str)](#apidoc.element.validator.isFullWidth.default)
1.  object <span class="apidocSignatureSpan">validator.isFullWidth.</span>fullWidth

#### [module validator.isHalfWidth](#apidoc.module.validator.isHalfWidth)
1.  [function <span class="apidocSignatureSpan">validator.isHalfWidth.</span>default (str)](#apidoc.element.validator.isHalfWidth.default)
1.  object <span class="apidocSignatureSpan">validator.isHalfWidth.</span>halfWidth

#### [module validator.isISO8601](#apidoc.module.validator.isISO8601)
1.  [function <span class="apidocSignatureSpan">validator.isISO8601.</span>default (str)](#apidoc.element.validator.isISO8601.default)
1.  object <span class="apidocSignatureSpan">validator.isISO8601.</span>iso8601



# <a name="apidoc.module.validator"></a>[module validator](#apidoc.module.validator)

#### <a name="apidoc.element.validator.blacklist"></a>[function <span class="apidocSignatureSpan">validator.</span>blacklist (str, chars)](#apidoc.element.validator.blacklist)
- description and source-code
```javascript
function blacklist(str, chars) {
  (0, _assertString2.default)(str);
  return str.replace(new RegExp('[' + chars + ']+', 'g'), '');
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.validator.contains"></a>[function <span class="apidocSignatureSpan">validator.</span>contains (str, elem)](#apidoc.element.validator.contains)
- description and source-code
```javascript
function contains(str, elem) {
  (0, _assertString2.default)(str);
  return str.indexOf((0, _toString2.default)(elem)) >= 0;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.validator.equals"></a>[function <span class="apidocSignatureSpan">validator.</span>equals (str, comparison)](#apidoc.element.validator.equals)
- description and source-code
```javascript
function equals(str, comparison) {
  (0, _assertString2.default)(str);
  return str === comparison;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.validator.escape"></a>[function <span class="apidocSignatureSpan">validator.</span>escape (str)](#apidoc.element.validator.escape)
- description and source-code
```javascript
function escape(str) {
      (0, _assertString2.default)(str);
      return str.replace(/&/g, '&amp;').replace(/"/g, '&quot;').replace(/'/g, '&#x27;').replace(/</g, '&lt;').replace(/>/g, '&gt
;').replace(/\//g, '&#x2F;').replace(/\\/g, '&#x5C;').replace(/'/g, '&#96;');
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.validator.isAfter"></a>[function <span class="apidocSignatureSpan">validator.</span>isAfter (str)](#apidoc.element.validator.isAfter)
- description and source-code
```javascript
function isAfter(str) {
  var date = arguments.length > 1 && arguments[1] !== undefined ? arguments[1] : String(new Date());

  (0, _assertString2.default)(str);
  var comparison = (0, _toDate2.default)(date);
  var original = (0, _toDate2.default)(str);
  return !!(original && comparison && original > comparison);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.validator.isAlpha"></a>[function <span class="apidocSignatureSpan">validator.</span>isAlpha (str)](#apidoc.element.validator.isAlpha)
- description and source-code
```javascript
function isAlpha(str) {
  var locale = arguments.length > 1 && arguments[1] !== undefined ? arguments[1] : 'en-US';

  (0, _assertString2.default)(str);
  if (locale in _alpha.alpha) {
    return _alpha.alpha[locale].test(str);
  }
  throw new Error('Invalid locale \'' + locale + '\'');
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.validator.isAlphanumeric"></a>[function <span class="apidocSignatureSpan">validator.</span>isAlphanumeric (str)](#apidoc.element.validator.isAlphanumeric)
- description and source-code
```javascript
function isAlphanumeric(str) {
  var locale = arguments.length > 1 && arguments[1] !== undefined ? arguments[1] : 'en-US';

  (0, _assertString2.default)(str);
  if (locale in _alpha.alphanumeric) {
    return _alpha.alphanumeric[locale].test(str);
  }
  throw new Error('Invalid locale \'' + locale + '\'');
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.validator.isAscii"></a>[function <span class="apidocSignatureSpan">validator.</span>isAscii (str)](#apidoc.element.validator.isAscii)
- description and source-code
```javascript
function isAscii(str) {
  (0, _assertString2.default)(str);
  return ascii.test(str);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.validator.isBase64"></a>[function <span class="apidocSignatureSpan">validator.</span>isBase64 (str)](#apidoc.element.validator.isBase64)
- description and source-code
```javascript
function isBase64(str) {
  (0, _assertString2.default)(str);
  var len = str.length;
  if (!len || len % 4 !== 0 || notBase64.test(str)) {
    return false;
  }
  var firstPaddingChar = str.indexOf('=');
  return firstPaddingChar === -1 || firstPaddingChar === len - 1 || firstPaddingChar === len - 2 && str[len - 1] === '=';
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.validator.isBefore"></a>[function <span class="apidocSignatureSpan">validator.</span>isBefore (str)](#apidoc.element.validator.isBefore)
- description and source-code
```javascript
function isBefore(str) {
  var date = arguments.length > 1 && arguments[1] !== undefined ? arguments[1] : String(new Date());

  (0, _assertString2.default)(str);
  var comparison = (0, _toDate2.default)(date);
  var original = (0, _toDate2.default)(str);
  return !!(original && comparison && original < comparison);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.validator.isBoolean"></a>[function <span class="apidocSignatureSpan">validator.</span>isBoolean (str)](#apidoc.element.validator.isBoolean)
- description and source-code
```javascript
function isBoolean(str) {
  (0, _assertString2.default)(str);
  return ['true', 'false', '1', '0'].indexOf(str) >= 0;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.validator.isByteLength"></a>[function <span class="apidocSignatureSpan">validator.</span>isByteLength (str, options)](#apidoc.element.validator.isByteLength)
- description and source-code
```javascript
function isByteLength(str, options) {
  (0, _assertString2.default)(str);
  var min = void 0;
  var max = void 0;
  if ((typeof options === 'undefined' ? 'undefined' : _typeof(options)) === 'object') {
    min = options.min || 0;
    max = options.max;
  } else {
    // backwards compatibility: isByteLength(str, min [, max])
    min = arguments[1];
    max = arguments[2];
  }
  var len = encodeURI(str).split(/%..|./).length - 1;
  return len >= min && (typeof max === 'undefined' || len <= max);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.validator.isCreditCard"></a>[function <span class="apidocSignatureSpan">validator.</span>isCreditCard (str)](#apidoc.element.validator.isCreditCard)
- description and source-code
```javascript
function isCreditCard(str) {
  (0, _assertString2.default)(str);
  var sanitized = str.replace(/[^0-9]+/g, '');
  if (!creditCard.test(sanitized)) {
    return false;
  }
  var sum = 0;
  var digit = void 0;
  var tmpNum = void 0;
  var shouldDouble = void 0;
  for (var i = sanitized.length - 1; i >= 0; i--) {
    digit = sanitized.substring(i, i + 1);
    tmpNum = parseInt(digit, 10);
    if (shouldDouble) {
      tmpNum *= 2;
      if (tmpNum >= 10) {
        sum += tmpNum % 10 + 1;
      } else {
        sum += tmpNum;
      }
    } else {
      sum += tmpNum;
    }
    shouldDouble = !shouldDouble;
  }
  return !!(sum % 10 === 0 ? sanitized : false);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.validator.isCurrency"></a>[function <span class="apidocSignatureSpan">validator.</span>isCurrency (str, options)](#apidoc.element.validator.isCurrency)
- description and source-code
```javascript
function isCurrency(str, options) {
  (0, _assertString2.default)(str);
  options = (0, _merge2.default)(options, default_currency_options);
  return currencyRegex(options).test(str);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.validator.isDataURI"></a>[function <span class="apidocSignatureSpan">validator.</span>isDataURI (str)](#apidoc.element.validator.isDataURI)
- description and source-code
```javascript
function isDataURI(str) {
  (0, _assertString2.default)(str);
  return dataURI.test(str);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.validator.isDecimal"></a>[function <span class="apidocSignatureSpan">validator.</span>isDecimal (str)](#apidoc.element.validator.isDecimal)
- description and source-code
```javascript
function isDecimal(str) {
  (0, _assertString2.default)(str);
  return str !== '' && decimal.test(str);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.validator.isDivisibleBy"></a>[function <span class="apidocSignatureSpan">validator.</span>isDivisibleBy (str, num)](#apidoc.element.validator.isDivisibleBy)
- description and source-code
```javascript
function isDivisibleBy(str, num) {
  (0, _assertString2.default)(str);
  return (0, _toFloat2.default)(str) % parseInt(num, 10) === 0;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.validator.isEmail"></a>[function <span class="apidocSignatureSpan">validator.</span>isEmail (str, options)](#apidoc.element.validator.isEmail)
- description and source-code
```javascript
function isEmail(str, options) {
  (0, _assertString2.default)(str);
  options = (0, _merge2.default)(options, default_email_options);

  if (options.require_display_name || options.allow_display_name) {
    var display_email = str.match(displayName);
    if (display_email) {
      str = display_email[1];
    } else if (options.require_display_name) {
      return false;
    }
  }

  var parts = str.split('@');
  var domain = parts.pop();
  var user = parts.join('@');

  var lower_domain = domain.toLowerCase();
  if (lower_domain === 'gmail.com' || lower_domain === 'googlemail.com') {
    user = user.replace(/\./g, '').toLowerCase();
  }

  if (!(0, _isByteLength2.default)(user, { max: 64 }) || !(0, _isByteLength2.default)(domain, { max: 256 })) {
    return false;
  }

  if (!(0, _isFQDN2.default)(domain, { require_tld: options.require_tld })) {
    return false;
  }

  if (user[0] === '"') {
    user = user.slice(1, user.length - 1);
    return options.allow_utf8_local_part ? quotedEmailUserUtf8.test(user) : quotedEmailUser.test(user);
  }

  var pattern = options.allow_utf8_local_part ? emailUserUtf8Part : emailUserPart;

  var user_parts = user.split('.');
  for (var i = 0; i < user_parts.length; i++) {
    if (!pattern.test(user_parts[i])) {
      return false;
    }
  }

  return true;
}
```
- example usage
```shell
...
### Server-side usage

Install the library with 'npm install validator'

'''javascript
var validator = require('validator');

validator.isEmail('foo@bar.com'); //=> true
'''

#### ES6

'''javascript
import validator from 'validator';
'''
...
```

#### <a name="apidoc.element.validator.isEmpty"></a>[function <span class="apidocSignatureSpan">validator.</span>isEmpty (str)](#apidoc.element.validator.isEmpty)
- description and source-code
```javascript
function isEmpty(str) {
  (0, _assertString2.default)(str);
  return str.length === 0;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.validator.isFQDN"></a>[function <span class="apidocSignatureSpan">validator.</span>isFQDN (str, options)](#apidoc.element.validator.isFQDN)
- description and source-code
```javascript
function isFDQN(str, options) {
  (0, _assertString2.default)(str);
  options = (0, _merge2.default)(options, default_fqdn_options);

<span class="apidocCodeCommentSpan">  /* Remove the optional trailing dot before checking validity */
</span>  if (options.allow_trailing_dot && str[str.length - 1] === '.') {
    str = str.substring(0, str.length - 1);
  }
  var parts = str.split('.');
  if (options.require_tld) {
    var tld = parts.pop();
    if (!parts.length || !/^([a-z\u00a1-\uffff]{2,}|xn[a-z0-9-]{2,})$/i.test(tld)) {
      return false;
    }
  }
  for (var part, i = 0; i < parts.length; i++) {
    part = parts[i];
    if (options.allow_underscores) {
      part = part.replace(/_/g, '');
    }
    if (!/^[a-z\u00a1-\uffff0-9-]+$/i.test(part)) {
      return false;
    }
    if (/[\uff01-\uff5e]/.test(part)) {
      // disallow full-width chars
      return false;
    }
    if (part[0] === '-' || part[part.length - 1] === '-') {
      return false;
    }
  }
  return true;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.validator.isFloat"></a>[function <span class="apidocSignatureSpan">validator.</span>isFloat (str, options)](#apidoc.element.validator.isFloat)
- description and source-code
```javascript
function isFloat(str, options) {
  (0, _assertString2.default)(str);
  options = options || {};
  if (str === '' || str === '.') {
    return false;
  }
  return float.test(str) && (!options.hasOwnProperty('min') || str >= options.min) && (!options.hasOwnProperty('max') || str <=
options.max) && (!options.hasOwnProperty('lt') || str < options.lt) && (!options.hasOwnProperty('gt') || str > options.gt);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.validator.isFullWidth"></a>[function <span class="apidocSignatureSpan">validator.</span>isFullWidth (str)](#apidoc.element.validator.isFullWidth)
- description and source-code
```javascript
function isFullWidth(str) {
  (0, _assertString2.default)(str);
  return fullWidth.test(str);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.validator.isHalfWidth"></a>[function <span class="apidocSignatureSpan">validator.</span>isHalfWidth (str)](#apidoc.element.validator.isHalfWidth)
- description and source-code
```javascript
function isHalfWidth(str) {
  (0, _assertString2.default)(str);
  return halfWidth.test(str);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.validator.isHexColor"></a>[function <span class="apidocSignatureSpan">validator.</span>isHexColor (str)](#apidoc.element.validator.isHexColor)
- description and source-code
```javascript
function isHexColor(str) {
  (0, _assertString2.default)(str);
  return hexcolor.test(str);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.validator.isHexadecimal"></a>[function <span class="apidocSignatureSpan">validator.</span>isHexadecimal (str)](#apidoc.element.validator.isHexadecimal)
- description and source-code
```javascript
function isHexadecimal(str) {
  (0, _assertString2.default)(str);
  return hexadecimal.test(str);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.validator.isIP"></a>[function <span class="apidocSignatureSpan">validator.</span>isIP (str)](#apidoc.element.validator.isIP)
- description and source-code
```javascript
function isIP(str) {
  var version = arguments.length > 1 && arguments[1] !== undefined ? arguments[1] : '';

  (0, _assertString2.default)(str);
  version = String(version);
  if (!version) {
    return isIP(str, 4) || isIP(str, 6);
  } else if (version === '4') {
    if (!ipv4Maybe.test(str)) {
      return false;
    }
    var parts = str.split('.').sort(function (a, b) {
      return a - b;
    });
    return parts[3] <= 255;
  } else if (version === '6') {
    var blocks = str.split(':');
    var foundOmissionBlock = false; // marker to indicate ::

    // At least some OS accept the last 32 bits of an IPv6 address
    // (i.e. 2 of the blocks) in IPv4 notation, and RFC 3493 says
    // that '::ffff:a.b.c.d' is valid for IPv4-mapped IPv6 addresses,
    // and '::a.b.c.d' is deprecated, but also valid.
    var foundIPv4TransitionBlock = isIP(blocks[blocks.length - 1], 4);
    var expectedNumberOfBlocks = foundIPv4TransitionBlock ? 7 : 8;

    if (blocks.length > expectedNumberOfBlocks) {
      return false;
    }
    // initial or final ::
    if (str === '::') {
      return true;
    } else if (str.substr(0, 2) === '::') {
      blocks.shift();
      blocks.shift();
      foundOmissionBlock = true;
    } else if (str.substr(str.length - 2) === '::') {
      blocks.pop();
      blocks.pop();
      foundOmissionBlock = true;
    }

    for (var i = 0; i < blocks.length; ++i) {
      // test for a :: which can not be at the string start/end
      // since those cases have been handled above
      if (blocks[i] === '' && i > 0 && i < blocks.length - 1) {
        if (foundOmissionBlock) {
          return false; // multiple :: in address
        }
        foundOmissionBlock = true;
      } else if (foundIPv4TransitionBlock && i === blocks.length - 1) {
        // it has been checked before that the last
        // block is a valid IPv4 address
      } else if (!ipv6Block.test(blocks[i])) {
        return false;
      }
    }
    if (foundOmissionBlock) {
      return blocks.length >= 1;
    }
    return blocks.length === expectedNumberOfBlocks;
  }
  return false;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.validator.isISBN"></a>[function <span class="apidocSignatureSpan">validator.</span>isISBN (str)](#apidoc.element.validator.isISBN)
- description and source-code
```javascript
function isISBN(str) {
  var version = arguments.length > 1 && arguments[1] !== undefined ? arguments[1] : '';

  (0, _assertString2.default)(str);
  version = String(version);
  if (!version) {
    return isISBN(str, 10) || isISBN(str, 13);
  }
  var sanitized = str.replace(/[\s-]+/g, '');
  var checksum = 0;
  var i = void 0;
  if (version === '10') {
    if (!isbn10Maybe.test(sanitized)) {
      return false;
    }
    for (i = 0; i < 9; i++) {
      checksum += (i + 1) * sanitized.charAt(i);
    }
    if (sanitized.charAt(9) === 'X') {
      checksum += 10 * 10;
    } else {
      checksum += 10 * sanitized.charAt(9);
    }
    if (checksum % 11 === 0) {
      return !!sanitized;
    }
  } else if (version === '13') {
    if (!isbn13Maybe.test(sanitized)) {
      return false;
    }
    for (i = 0; i < 12; i++) {
      checksum += factor[i % 2] * sanitized.charAt(i);
    }
    if (sanitized.charAt(12) - (10 - checksum % 10) % 10 === 0) {
      return !!sanitized;
    }
  }
  return false;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.validator.isISIN"></a>[function <span class="apidocSignatureSpan">validator.</span>isISIN (str)](#apidoc.element.validator.isISIN)
- description and source-code
```javascript
function isISIN(str) {
  (0, _assertString2.default)(str);
  if (!isin.test(str)) {
    return false;
  }

  var checksumStr = str.replace(/[A-Z]/g, function (character) {
    return parseInt(character, 36);
  });

  var sum = 0;
  var digit = void 0;
  var tmpNum = void 0;
  var shouldDouble = true;
  for (var i = checksumStr.length - 2; i >= 0; i--) {
    digit = checksumStr.substring(i, i + 1);
    tmpNum = parseInt(digit, 10);
    if (shouldDouble) {
      tmpNum *= 2;
      if (tmpNum >= 10) {
        sum += tmpNum + 1;
      } else {
        sum += tmpNum;
      }
    } else {
      sum += tmpNum;
    }
    shouldDouble = !shouldDouble;
  }

  return parseInt(str.substr(str.length - 1), 10) === (10000 - sum) % 10;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.validator.isISO8601"></a>[function <span class="apidocSignatureSpan">validator.</span>isISO8601 (str)](#apidoc.element.validator.isISO8601)
- description and source-code
```javascript
isISO8601 = function (str) {
  (0, _assertString2.default)(str);
  return iso8601.test(str);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.validator.isISSN"></a>[function <span class="apidocSignatureSpan">validator.</span>isISSN (str)](#apidoc.element.validator.isISSN)
- description and source-code
```javascript
function isISSN(str) {
  var options = arguments.length > 1 && arguments[1] !== undefined ? arguments[1] : {};

  (0, _assertString2.default)(str);
  var testIssn = issn;
  testIssn = options.require_hyphen ? testIssn.replace('?', '') : testIssn;
  testIssn = options.case_sensitive ? new RegExp(testIssn) : new RegExp(testIssn, 'i');
  if (!testIssn.test(str)) {
    return false;
  }
  var issnDigits = str.replace('-', '');
  var position = 8;
  var checksum = 0;
  var _iteratorNormalCompletion = true;
  var _didIteratorError = false;
  var _iteratorError = undefined;

  try {
    for (var _iterator = issnDigits[Symbol.iterator](), _step; !(_iteratorNormalCompletion = (_step = _iterator.next()).done); _iteratorNormalCompletion
 = true) {
      var digit = _step.value;

      var digitValue = digit.toUpperCase() === 'X' ? 10 : +digit;
      checksum += digitValue * position;
      --position;
    }
  } catch (err) {
    _didIteratorError = true;
    _iteratorError = err;
  } finally {
    try {
      if (!_iteratorNormalCompletion && _iterator.return) {
        _iterator.return();
      }
    } finally {
      if (_didIteratorError) {
        throw _iteratorError;
      }
    }
  }

  return checksum % 11 === 0;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.validator.isIn"></a>[function <span class="apidocSignatureSpan">validator.</span>isIn (str, options)](#apidoc.element.validator.isIn)
- description and source-code
```javascript
function isIn(str, options) {
  (0, _assertString2.default)(str);
  var i = void 0;
  if (Object.prototype.toString.call(options) === '[object Array]') {
    var array = [];
    for (i in options) {
      if ({}.hasOwnProperty.call(options, i)) {
        array[i] = (0, _toString2.default)(options[i]);
      }
    }
    return array.indexOf(str) >= 0;
  } else if ((typeof options === 'undefined' ? 'undefined' : _typeof(options)) === 'object') {
    return options.hasOwnProperty(str);
  } else if (options && typeof options.indexOf === 'function') {
    return options.indexOf(str) >= 0;
  }
  return false;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.validator.isInt"></a>[function <span class="apidocSignatureSpan">validator.</span>isInt (str, options)](#apidoc.element.validator.isInt)
- description and source-code
```javascript
function isInt(str, options) {
  (0, _assertString2.default)(str);
  options = options || {};

  // Get the regex to use for testing, based on whether
  // leading zeroes are allowed or not.
  var regex = options.hasOwnProperty('allow_leading_zeroes') && !options.allow_leading_zeroes ? int : intLeadingZeroes;

  // Check min/max/lt/gt
  var minCheckPassed = !options.hasOwnProperty('min') || str >= options.min;
  var maxCheckPassed = !options.hasOwnProperty('max') || str <= options.max;
  var ltCheckPassed = !options.hasOwnProperty('lt') || str < options.lt;
  var gtCheckPassed = !options.hasOwnProperty('gt') || str > options.gt;

  return regex.test(str) && minCheckPassed && maxCheckPassed && ltCheckPassed && gtCheckPassed;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.validator.isJSON"></a>[function <span class="apidocSignatureSpan">validator.</span>isJSON (str)](#apidoc.element.validator.isJSON)
- description and source-code
```javascript
function isJSON(str) {
  (0, _assertString2.default)(str);
  try {
    var obj = JSON.parse(str);
    return !!obj && (typeof obj === 'undefined' ? 'undefined' : _typeof(obj)) === 'object';
  } catch (e) {/* ignore */}
  return false;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.validator.isLength"></a>[function <span class="apidocSignatureSpan">validator.</span>isLength (str, options)](#apidoc.element.validator.isLength)
- description and source-code
```javascript
function isLength(str, options) {
  (0, _assertString2.default)(str);
  var min = void 0;
  var max = void 0;
  if ((typeof options === 'undefined' ? 'undefined' : _typeof(options)) === 'object') {
    min = options.min || 0;
    max = options.max;
  } else {
    // backwards compatibility: isLength(str, min [, max])
    min = arguments[1];
    max = arguments[2];
  }
  var surrogatePairs = str.match(/[\uD800-\uDBFF][\uDC00-\uDFFF]/g) || [];
  var len = str.length - surrogatePairs.length;
  return len >= min && (typeof max === 'undefined' || len <= max);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.validator.isLowercase"></a>[function <span class="apidocSignatureSpan">validator.</span>isLowercase (str)](#apidoc.element.validator.isLowercase)
- description and source-code
```javascript
function isLowercase(str) {
  (0, _assertString2.default)(str);
  return str === str.toLowerCase();
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.validator.isMACAddress"></a>[function <span class="apidocSignatureSpan">validator.</span>isMACAddress (str)](#apidoc.element.validator.isMACAddress)
- description and source-code
```javascript
function isMACAddress(str) {
  (0, _assertString2.default)(str);
  return macAddress.test(str);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.validator.isMD5"></a>[function <span class="apidocSignatureSpan">validator.</span>isMD5 (str)](#apidoc.element.validator.isMD5)
- description and source-code
```javascript
function isMD5(str) {
  (0, _assertString2.default)(str);
  return md5.test(str);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.validator.isMobilePhone"></a>[function <span class="apidocSignatureSpan">validator.</span>isMobilePhone (str, locale)](#apidoc.element.validator.isMobilePhone)
- description and source-code
```javascript
function isMobilePhone(str, locale) {
  (0, _assertString2.default)(str);
  if (locale in phones) {
    return phones[locale].test(str);
  }
  return false;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.validator.isMongoId"></a>[function <span class="apidocSignatureSpan">validator.</span>isMongoId (str)](#apidoc.element.validator.isMongoId)
- description and source-code
```javascript
function isMongoId(str) {
  (0, _assertString2.default)(str);
  return (0, _isHexadecimal2.default)(str) && str.length === 24;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.validator.isMultibyte"></a>[function <span class="apidocSignatureSpan">validator.</span>isMultibyte (str)](#apidoc.element.validator.isMultibyte)
- description and source-code
```javascript
function isMultibyte(str) {
  (0, _assertString2.default)(str);
  return multibyte.test(str);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.validator.isNumeric"></a>[function <span class="apidocSignatureSpan">validator.</span>isNumeric (str)](#apidoc.element.validator.isNumeric)
- description and source-code
```javascript
function isNumeric(str) {
  (0, _assertString2.default)(str);
  return numeric.test(str);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.validator.isSurrogatePair"></a>[function <span class="apidocSignatureSpan">validator.</span>isSurrogatePair (str)](#apidoc.element.validator.isSurrogatePair)
- description and source-code
```javascript
function isSurrogatePair(str) {
  (0, _assertString2.default)(str);
  return surrogatePair.test(str);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.validator.isURL"></a>[function <span class="apidocSignatureSpan">validator.</span>isURL (url, options)](#apidoc.element.validator.isURL)
- description and source-code
```javascript
function isURL(url, options) {
  (0, _assertString2.default)(url);
  if (!url || url.length >= 2083 || /[\s<>]/.test(url)) {
    return false;
  }
  if (url.indexOf('mailto:') === 0) {
    return false;
  }
  options = (0, _merge2.default)(options, default_url_options);
  var protocol = void 0,
      auth = void 0,
      host = void 0,
      hostname = void 0,
      port = void 0,
      port_str = void 0,
      split = void 0,
      ipv6 = void 0;

  split = url.split('#');
  url = split.shift();

  split = url.split('?');
  url = split.shift();

  split = url.split('://');
  if (split.length > 1) {
    protocol = split.shift();
    if (options.require_valid_protocol && options.protocols.indexOf(protocol) === -1) {
      return false;
    }
  } else if (options.require_protocol) {
    return false;
  } else if (options.allow_protocol_relative_urls && url.substr(0, 2) === '//') {
    split[0] = url.substr(2);
  }
  url = split.join('://');

  split = url.split('/');
  url = split.shift();

  if (url === '' && !options.require_host) {
    return true;
  }

  split = url.split('@');
  if (split.length > 1) {
    auth = split.shift();
    if (auth.indexOf(':') >= 0 && auth.split(':').length > 2) {
      return false;
    }
  }
  hostname = split.join('@');

  port_str = ipv6 = null;
  var ipv6_match = hostname.match(wrapped_ipv6);
  if (ipv6_match) {
    host = '';
    ipv6 = ipv6_match[1];
    port_str = ipv6_match[2] || null;
  } else {
    split = hostname.split(':');
    host = split.shift();
    if (split.length) {
      port_str = split.join(':');
    }
  }

  if (port_str !== null) {
    port = parseInt(port_str, 10);
    if (!/^[0-9]+$/.test(port_str) || port <= 0 || port > 65535) {
      return false;
    }
  }

  if (!(0, _isIP2.default)(host) && !(0, _isFQDN2.default)(host, options) && (!ipv6 || !(0, _isIP2.default)(ipv6, 6)) && host !== '
localhost') {
    return false;
  }

  host = host || ipv6;

  if (options.host_whitelist && !checkHost(host, options.host_whitelist)) {
    return false;
  }
  if (options.host_blacklist && checkHost(host, options.host_blacklist)) {
    return false;
  }

  return true;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.validator.isUUID"></a>[function <span class="apidocSignatureSpan">validator.</span>isUUID (str)](#apidoc.element.validator.isUUID)
- description and source-code
```javascript
function isUUID(str) {
  var version = arguments.length > 1 && arguments[1] !== undefined ? arguments[1] : 'all';

  (0, _assertString2.default)(str);
  var pattern = uuid[version];
  return pattern && pattern.test(str);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.validator.isUppercase"></a>[function <span class="apidocSignatureSpan">validator.</span>isUppercase (str)](#apidoc.element.validator.isUppercase)
- description and source-code
```javascript
function isUppercase(str) {
  (0, _assertString2.default)(str);
  return str === str.toUpperCase();
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.validator.isVariableWidth"></a>[function <span class="apidocSignatureSpan">validator.</span>isVariableWidth (str)](#apidoc.element.validator.isVariableWidth)
- description and source-code
```javascript
function isVariableWidth(str) {
  (0, _assertString2.default)(str);
  return _isFullWidth.fullWidth.test(str) && _isHalfWidth.halfWidth.test(str);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.validator.isWhitelisted"></a>[function <span class="apidocSignatureSpan">validator.</span>isWhitelisted (str, chars)](#apidoc.element.validator.isWhitelisted)
- description and source-code
```javascript
function isWhitelisted(str, chars) {
  (0, _assertString2.default)(str);
  for (var i = str.length - 1; i >= 0; i--) {
    if (chars.indexOf(str[i]) === -1) {
      return false;
    }
  }
  return true;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.validator.ltrim"></a>[function <span class="apidocSignatureSpan">validator.</span>ltrim (str, chars)](#apidoc.element.validator.ltrim)
- description and source-code
```javascript
function ltrim(str, chars) {
  (0, _assertString2.default)(str);
  var pattern = chars ? new RegExp('^[' + chars + ']+', 'g') : /^\s+/g;
  return str.replace(pattern, '');
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.validator.matches"></a>[function <span class="apidocSignatureSpan">validator.</span>matches (str, pattern, modifiers)](#apidoc.element.validator.matches)
- description and source-code
```javascript
function matches(str, pattern, modifiers) {
  (0, _assertString2.default)(str);
  if (Object.prototype.toString.call(pattern) !== '[object RegExp]') {
    pattern = new RegExp(pattern, modifiers);
  }
  return pattern.test(str);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.validator.normalizeEmail"></a>[function <span class="apidocSignatureSpan">validator.</span>normalizeEmail (email, options)](#apidoc.element.validator.normalizeEmail)
- description and source-code
```javascript
function normalizeEmail(email, options) {
  options = (0, _merge2.default)(options, default_normalize_email_options);

  if (!(0, _isEmail2.default)(email)) {
    return false;
  }

  var raw_parts = email.split('@');
  var domain = raw_parts.pop();
  var user = raw_parts.join('@');
  var parts = [user, domain];

  // The domain is always lowercased, as it's case-insensitive per RFC 1035
  parts[1] = parts[1].toLowerCase();

  if (parts[1] === 'gmail.com' || parts[1] === 'googlemail.com') {
    // Address is GMail
    if (options.gmail_remove_subaddress) {
      parts[0] = parts[0].split('+')[0];
    }
    if (options.gmail_remove_dots) {
      parts[0] = parts[0].replace(/\./g, '');
    }
    if (!parts[0].length) {
      return false;
    }
    if (options.all_lowercase || options.gmail_lowercase) {
      parts[0] = parts[0].toLowerCase();
    }
    parts[1] = options.gmail_convert_googlemaildotcom ? 'gmail.com' : parts[1];
  } else if (~icloud_domains.indexOf(parts[1])) {
    // Address is iCloud
    if (options.icloud_remove_subaddress) {
      parts[0] = parts[0].split('+')[0];
    }
    if (!parts[0].length) {
      return false;
    }
    if (options.all_lowercase || options.icloud_lowercase) {
      parts[0] = parts[0].toLowerCase();
    }
  } else if (~outlookdotcom_domains.indexOf(parts[1])) {
    // Address is Outlook.com
    if (options.outlookdotcom_remove_subaddress) {
      parts[0] = parts[0].split('+')[0];
    }
    if (!parts[0].length) {
      return false;
    }
    if (options.all_lowercase || options.outlookdotcom_lowercase) {
      parts[0] = parts[0].toLowerCase();
    }
  } else if (~yahoo_domains.indexOf(parts[1])) {
    // Address is Yahoo
    if (options.yahoo_remove_subaddress) {
      var components = parts[0].split('-');
      parts[0] = components.length > 1 ? components.slice(0, -1).join('-') : components[0];
    }
    if (!parts[0].length) {
      return false;
    }
    if (options.all_lowercase || options.yahoo_lowercase) {
      parts[0] = parts[0].toLowerCase();
    }
  } else if (options.all_lowercase) {
    // Any other address
    parts[0] = parts[0].toLowerCase();
  }
  return parts.join('@');
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.validator.rtrim"></a>[function <span class="apidocSignatureSpan">validator.</span>rtrim (str, chars)](#apidoc.element.validator.rtrim)
- description and source-code
```javascript
function rtrim(str, chars) {
  (0, _assertString2.default)(str);
  var pattern = chars ? new RegExp('[' + chars + ']') : /\s/;

  var idx = str.length - 1;
  while (idx >= 0 && pattern.test(str[idx])) {
    idx--;
  }

  return idx < str.length ? str.substr(0, idx + 1) : str;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.validator.stripLow"></a>[function <span class="apidocSignatureSpan">validator.</span>stripLow (str, keep_new_lines)](#apidoc.element.validator.stripLow)
- description and source-code
```javascript
function stripLow(str, keep_new_lines) {
  (0, _assertString2.default)(str);
  var chars = keep_new_lines ? '\\x00-\\x09\\x0B\\x0C\\x0E-\\x1F\\x7F' : '\\x00-\\x1F\\x7F';
  return (0, _blacklist2.default)(str, chars);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.validator.toBoolean"></a>[function <span class="apidocSignatureSpan">validator.</span>toBoolean (str, strict)](#apidoc.element.validator.toBoolean)
- description and source-code
```javascript
function toBoolean(str, strict) {
  (0, _assertString2.default)(str);
  if (strict) {
    return str === '1' || str === 'true';
  }
  return str !== '0' && str !== 'false' && str !== '';
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.validator.toDate"></a>[function <span class="apidocSignatureSpan">validator.</span>toDate (date)](#apidoc.element.validator.toDate)
- description and source-code
```javascript
function toDate(date) {
  (0, _assertString2.default)(date);
  date = Date.parse(date);
  return !isNaN(date) ? new Date(date) : null;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.validator.toFloat"></a>[function <span class="apidocSignatureSpan">validator.</span>toFloat (str)](#apidoc.element.validator.toFloat)
- description and source-code
```javascript
function toFloat(str) {
  (0, _assertString2.default)(str);
  return parseFloat(str);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.validator.toInt"></a>[function <span class="apidocSignatureSpan">validator.</span>toInt (str, radix)](#apidoc.element.validator.toInt)
- description and source-code
```javascript
function toInt(str, radix) {
  (0, _assertString2.default)(str);
  return parseInt(str, radix || 10);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.validator.trim"></a>[function <span class="apidocSignatureSpan">validator.</span>trim (str, chars)](#apidoc.element.validator.trim)
- description and source-code
```javascript
function trim(str, chars) {
  return (0, _rtrim2.default)((0, _ltrim2.default)(str, chars), chars);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.validator.unescape"></a>[function <span class="apidocSignatureSpan">validator.</span>unescape (str)](#apidoc.element.validator.unescape)
- description and source-code
```javascript
function unescape(str) {
      (0, _assertString2.default)(str);
      return str.replace(/&amp;/g, '&').replace(/&quot;/g, '"').replace(/&#x27;/g, "'").replace(/&lt;/g, '<').replace(/&gt;/g, '>').
replace(/&#x2F;/g, '/').replace(/&#96;/g, ''');
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.validator.whitelist"></a>[function <span class="apidocSignatureSpan">validator.</span>whitelist (str, chars)](#apidoc.element.validator.whitelist)
- description and source-code
```javascript
function whitelist(str, chars) {
  (0, _assertString2.default)(str);
  return str.replace(new RegExp('[^' + chars + ']+', 'g'), '');
}
```
- example usage
```shell
n/a
```



# <a name="apidoc.module.validator.isFullWidth"></a>[module validator.isFullWidth](#apidoc.module.validator.isFullWidth)

#### <a name="apidoc.element.validator.isFullWidth.default"></a>[function <span class="apidocSignatureSpan">validator.isFullWidth.</span>default (str)](#apidoc.element.validator.isFullWidth.default)
- description and source-code
```javascript
function isFullWidth(str) {
  (0, _assertString2.default)(str);
  return fullWidth.test(str);
}
```
- example usage
```shell
n/a
```



# <a name="apidoc.module.validator.isHalfWidth"></a>[module validator.isHalfWidth](#apidoc.module.validator.isHalfWidth)

#### <a name="apidoc.element.validator.isHalfWidth.default"></a>[function <span class="apidocSignatureSpan">validator.isHalfWidth.</span>default (str)](#apidoc.element.validator.isHalfWidth.default)
- description and source-code
```javascript
function isHalfWidth(str) {
  (0, _assertString2.default)(str);
  return halfWidth.test(str);
}
```
- example usage
```shell
n/a
```



# <a name="apidoc.module.validator.isISO8601"></a>[module validator.isISO8601](#apidoc.module.validator.isISO8601)

#### <a name="apidoc.element.validator.isISO8601.default"></a>[function <span class="apidocSignatureSpan">validator.isISO8601.</span>default (str)](#apidoc.element.validator.isISO8601.default)
- description and source-code
```javascript
default = function (str) {
  (0, _assertString2.default)(str);
  return iso8601.test(str);
}
```
- example usage
```shell
n/a
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
