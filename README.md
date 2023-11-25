# @kelysty/stylelint-config

## Install

Using `npm`:

```bash
npm install --save-dev stylelint postcss @kelysty/stylelint-config
```

Using `yarn`:

```bash
yarn add --dev stylelint postcss @kelysty/stylelint-config
```

## Usage

Add `.stylelintrc.js` file in the project root with the following content:

```js
module.exports = {
  extends: ['@kelysty/stylelint-config'],
};
```

### Prettier

If you are using Prettier, extend root config with the additional rules:

```js
module.exports = {
  extends: ['@kelysty/stylelint-config', '@kelysty/stylelint-config/prettier'],
};
```

### Order

If you want to order properties in your css files, extend root config with the additional rules:

```js
module.exports = {
  extends: ['@kelysty/stylelint-config', '@kelysty/stylelint-config/order'],
};
```

### Scripts

Do not forget to add following scripts in your `package.json` file:

```json
  "scripts": {
    "lint": "yarn run lint:styles && yarn run lint:other",
    "lint:styles": "stylelint '**/*.{css,scss}' --report-needless-disables",
    "lint:other": "yarn run prettier -- --check",
  }
```
