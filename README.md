![Greenlight Logo](https://gitcdn.link/repo/greenlight-ci/brand/master/logo/banner.svg)

# Config Schema [![version][npm-version]][npm-url] [![License][license-image]][license-url] [![Build Status][travis-image]][travis-url]

> Defines a [Greenlight][] configuration file format & schema

## Specification

### Versions

version                | status     
---------------------- | -----------
[`1.0.0`](spec/1.0.0/) | development

## JSON Schema

Available as an `npm` package for validation purposes, compatible with any [JSON Schema][] validation tool

```bash
npm install --production --save @greenlight/schema-config
```

## API

```js
const { schema, regex } = require('@greenlight/schema-config')
```

---

> License: [ISC][license-url] • 
> Copyright: [greenlight.ci](https://greenlight.ci) • 
> Github: [@greenlight-CI](https://github.com/greenlight-CI) • 
> Twitter: [@greenlightCI](https://twitter.com/greenlightCI)

[greenlight]: https://greenlight.ci

[json schema]: http://json-schema.org

[license-image]: https://img.shields.io/github/license/greenlight/schema-config.svg?style=flat-square

[license-url]: http://choosealicense.com/licenses/isc/

[npm-url]: https://www.npmjs.com/package/@greenlight/schema-config

[npm-version]: https://img.shields.io/npm/v/@greenlight/schema-config.svg?style=flat-square

[travis-image]: https://img.shields.io/travis/greenlight-ci/schema-config.svg?style=flat-square

[travis-url]: https://travis-ci.org/greenlight-ci/schema-config
