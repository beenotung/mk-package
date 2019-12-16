# mk-package

copy package.json into dist directory for npm publish

[![npm Package Version](https://img.shields.io/npm/v/mk-package.svg?maxAge=2592000)](https://www.npmjs.com/package/mk-package)

This allow the library consumer to import required files instead of loading the whole library easily.

`main` and `types` are auto updated if `index.js` and `index.d.ts` exists.
Otherwise, the fields will be left blank.

## Example library with moved package.json
```
import { aFunc } from 'alib/aModule'
```

## Example library without moved package.json
```
import { aFunc } from 'alib/dist/aModule'
```
