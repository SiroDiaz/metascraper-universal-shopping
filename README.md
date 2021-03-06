# metascraper-universal-shopping

[![npm](https://img.shields.io/npm/v/@sirodiaz/metascraper-universal-shopping.svg?style=flat-square)](https://www.npmjs.com/package/@sirodiaz/metascraper-universal-shopping)
[![Dependency Status](https://david-dm.org/samirrayani/metascraper-shopping.svg?style=flat-square)](https://david-dm.org/samirrayani/metascraper-shopping)

> A custom rule bundle for [@microlinkhq/metascraper](https://github.com/microlinkhq/metascraper) to get product information from HTML markup on merchant websites

## Install

```bash
$ npm install @sirodiaz/metascraper-universal-shopping --save
```

## Usage

```javascript
'use strict'

const metascraper = require('metascraper')([
  require('@sirodiaz/metascraper-universal-shopping')(),
  require('metascraper-title')(),
  require('metascraper-image')(),
  require('metascraper-url')()
]);
const got = require('got');

const goShopping = async () => {
  const targetUrl = '<an URL from any e-commerce website>';
  const { body: html, url } = await got(targetUrl);
  const metadata = await metascraper({ html, url });
  console.log(metadata);
};

goShopping();

/*
metadata: {
  title:        [String]
  image:        [String]
  url:          [String]
  price:        [Float]
  currency:     [String]
  condition:    [String]
  sku:          [String]
  mpn:          [String]
  availability: [String]
  asin:         [String]
}
*/
```

## License

**@SiroDiaz/metascraper-universal-shopping** © 2022 Siro Díaz, Released under the [MIT](https://github.com/SiroDiaz/metascraper-universal-shopping/blob/main/LICENSE.md) License.

**@sami/metascraper-shopping** © 2019-2022 Samir Rayani, Released under the [MIT](https://github.com/samirrayani/metascraper-shopping/blob/master/LICENSE.md) License.
