# eslint-config-betabong

[![npm](https://img.shields.io/npm/v/eslint-config-betabong?color=a1b858&label=NPM)](https://npmjs.com/package/eslint-config-betabong)

Based on [antfu/eslint-config](https://npmjs.com/package/@antfu/eslint-config), apart from the following changes:

-   **Semi quotes, no single**
-   **Slightly less strict:** e.g. Only warn on unused vars

Other than that, it's the same as the original:

-   Auto fix for formatting (aimed to be used standalone without Prettier)
-   Designed to work with TypeScript, Vue out-of-box
-   Lint also for json, yaml, markdown
-   Sorted imports, dangling commas
-   Reasonable defaults, best practices, only one-line of config

## Usage

### Install

```bash
yarn add -D eslint eslint-config-betabong
```

### Config `.eslintrc`

```json
{
	"extends": "@betabong"
}
```

> You don't need `.eslintignore` normally as it has been provided by the preset.

### Add script for package.json

For example:

```json
{
	"scripts": {
		"lint": "eslint .",
		"lint:fix": "eslint . --fix"
	}
}
```

### Config VS Code auto fix

Install [VS Code ESLint extension](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint) and create `.vscode/settings.json`

```json
{
	"prettier.enable": false,
	"editor.formatOnSave": false,
	"editor.codeActionsOnSave": {
		"source.fixAll.eslint": true
	}
}
```

You can also do it on a project basis, add `.vscode/settings.json` to your project root.

### TypeScript Aware Rules

Type aware rules are enabled when a `tsconfig.eslint.json` is found in the project root, which will introduce some stricter rules into your project. If you want to enable it while have no `tsconfig.eslint.json` in the project root, you can change tsconfig name by modifying `ESLINT_TSCONFIG` env.

```js
// .eslintrc.js
process.env.ESLINT_TSCONFIG = 'tsconfig.json';

module.exports = {
	extends: '@antfu',
};
```

## Extended Reading

Learn more about the context - [Why I don't use Prettier (by @antfu)](https://antfu.me/posts/why-not-prettier).

## License

[MIT](./LICENSE) License &copy; 2022-PRESENT [Severin Klaus](https://github.com/betabong)
