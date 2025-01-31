# hd-scripts [![NPM Version](https://img.shields.io/npm/v/hd-scripts.svg)](https://www.npmjs.com/package/hd-scripts) [![NPM License](https://img.shields.io/npm/l/hd-scripts.svg)](https://www.npmjs.com/package/hd-scripts) [![tests](https://github.com/hugomrdias/hd-scripts/actions/workflows/main.yml/badge.svg)](https://github.com/hugomrdias/hd-scripts/actions/workflows/main.yml)

> My personal config and scripts for projects

## Install

```
$ npm install hd-scripts
```

## Usage

`package.json`

```json
"main": "src/index.js",
"types": "dist/src/index.d.ts",
"files": [
  "dist/src",
  "src",
  "index.js",
  "cli.js"
],
"scripts": {
  "lint": "eslint **/*.js && prettier --check **/*.{js,ts,yml,json} --ignore-path .gitignore && tsc"
},
"simple-git-hooks": {
  "pre-commit": "npx lint-staged"
},
"lint-staged": {
  "*.{js,ts,md,yml,json}": "prettier --write",
  "*.js": "eslint --fix"
},
"eslintConfig": {
  "extends": "./node_modules/hd-scripts/eslint/index.js",
  "ignorePatterns": [
    "node_modules",
    "coverage",
    "dist",
    "docs"
  ]
},
"prettier": "hd-scripts/prettier.config.js"

```

`tsconfig.json`

```json
{
  "extends": "hd-scripts/tsconfig.json",
  "compilerOptions": {
    "outDir": "dist",
    "composite": false,
    "incremental": false
  },
  "include": ["src", "test.js", "cli.js", "package.json"]
}
```

## License

MIT © [Hugo Dias](http://hugodias.me)
