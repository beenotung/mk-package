# mk-package

copy package.json into dist directory for npm publish

[![npm Package Version](https://img.shields.io/npm/v/mk-package.svg?maxAge=2592000)](https://www.npmjs.com/package/mk-package)

This allows the library consumer to import required files instead of loading the whole library easily.

`main` and `types` are auto updated if `index.js` and `index.d.ts` exists.
Otherwise, the fields will be left blank.

## Example library with moved package.json
```
import { aFunc } from 'a-lib/aModule'
```

## Example library without moved package.json
```
import { aFunc } from 'a-lib/dist/aModule'
```

## Setup Example

You can use mk-package in last step of build pipeline or in the `postbuild` hook, then run `npm publish` inside the `dist` directory

**package.json**:
```json
{
  "scripts": {
    "build": "tsc && mk-package",
    "publish": "npm run build && cd dist && npm publish"
  },
  "devDependencies": {
    "mk-package": "^1.0.0"
  }
}
```

**tsconfig.json**
```json
{
  "compilerOptions": {
    "outDir": "dist"
  },
  "include": [
    "src/**/*.ts"
  ]
}
```

Details see [./example](./example)
