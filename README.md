# VSCode-ESLint-Prettier-Airbnb-Style-Guide-Setup-And-Typescript

`$. npm i -g eslint typescript`

**First install `ESlint` and `Prettier` extensions on your vscode**

**Set Format onSave**

Before Creating React App Do this: 

1. `$. npm iniy -y`
2. change the main in the `index.js` to `index.ts` in `package.json`
3. `$. npm i -D eslint prettier eslint-plugin-prettier eslint-config-prettier eslint-plugin-react eslint-config-react eslint-plugin-react-hooks`

Now Add `airbnb` style guide

1. `$. npx install-peerdeps --dev eslint-config-airbnb`
2. `$. eslint --init` => then here answer some questions

eslintrc.json

```js
{
  "extends": ["airbnb", "prettier", "plugin:react/recommended", "plugin:prettier/recommended", "eslint:recommended"]
  "plugins": ["prettier"],
  "rules: {
    "prettier/prettier": "error",
    "no-unused-vars": "error",
    "no-console": "error",
    "react/display-name": "off",
    "react-hooks/rules-of-hooks": "error",
    "react-hooks/exhaustive-deps": "warn",
    "no-useless-escape": "off",
  }
}
```

and finally to autoSave Eslint rules: create a folder called `.vscode` in the root folder and inside of it create a file called `settings.json`:

```js
{
    "editor.codeActionsOnSave": {
      "source.fixAll.eslint": true
    },
    "eslint.validate": ["javascript"]
}
```


# Typescript => Eslint-Prettier-airbnb-config

## Install

`$. yarn create react-app app --template typescript`

## NPM Packages

1. @typescript-eslint/eslint-plugin
2. @typescript-eslint/parser
3. eslint-config-airbnb-typescript
4. eslint-config-prettier
5. eslint-plugin-import (Airbnb peer)
6. eslint-plugin-jest
7. eslint-plugin-jsx-a11y (Airbnb peer)
8. eslint-plugin-prettier
9. eslint-plugin-react (Airbnb peer)
10. eslint-plugin-react-hooks (Airbnb peer)
11. prettier

We’ll be adding the following packages:

`$. npm install typescript eslint prettier eslint-config-airbnb-typescript-prettier --save-dev`

## Install ESlint

Install the ESLint packages for TypeScript and Jest support. Note, ESLint is installed with create-react-app, so you don’t need to explicitly install it.

`$. yarn add -D @typescript-eslint/eslint-plugin @typescript-eslint/parser eslint-config-airbnb-typescript eslint-plugin-jest`

Then install the packages for Airbnb config. This command will work for Yarn or NPM.

`$. npx install-peerdeps --dev eslint-config-airbnb`

## Prettier

`$. yarn add -D prettier eslint-config-prettier eslint-plugin-prettier`

## ESLint Config

The ESLint config will look something like this:

```js
module.exports = {
  extends: [
    'airbnb-typescript',
    'airbnb/hooks',
    'plugin:@typescript-eslint/recommended',
    'plugin:jest/recommended',
    'plugin:prettier/recommended'
  ],
  plugins: ['react', '@typescript-eslint', 'jest'],
  env: {
    browser: true,
    es6: true,
    jest: true,
  },
  globals: {
    Atomics: 'readonly',
    SharedArrayBuffer: 'readonly',
  },
  parser: '@typescript-eslint/parser',
  parserOptions: {
    ecmaFeatures: {
      jsx: true,
    },
    ecmaVersion: 2018,
    sourceType: 'module',
    project: './tsconfig.json',
  },
  rules: {
    'linebreak-style': 'off',
    'prettier/prettier': [
      'error',
      {
        endOfLine: 'auto',
      },
    ],
  },
};
```

## Scripts

Lint and format with these scripts:

```js
"scripts": {
  "format": "prettier --write src/**/*.ts{,x}",
  "lint": "tsc --noEmit && eslint src/**/*.ts{,x}"
}
```

## Install Eslint Plugins

`$. npm install eslint-plugin-import@^2.22.0 \
            eslint-plugin-jsx-a11y@^6.3.1 \
            eslint-plugin-react@^7.20.3 \
            eslint-plugin-react-hooks@^4.0.8 \
            @typescript-eslint/eslint-plugin@^4.4.1 \
            --save-dev`
            
## If you don't need React Support

`$. npm install eslint-plugin-import@^2.22.0 \
            @typescript-eslint/eslint-plugin@^4.4.1 \
            --save-dev`
            
 
 ## Configure Eslint
 
 Add "extends": "airbnb-typescript" to your ESLint config file.

If you don't need React support, add "extends": "airbnb-typescript/base" instead.

An example .eslintrc.js:

```js
module.exports = {
  extends: ['airbnb-typescript'],
};
```


## Configure the ESLint TypeScript parser

This config requires knowledge of your TypeScript config.

In your ESLint config, set parserOptions.project to the path of your tsconfig.json.

For example:

```js
module.exports = {
   extends: ['airbnb-typescript'],
+  parserOptions: {
+    project: './tsconfig.json',
+  }
 };
```

## Run ESLint

Open a terminal to the root of your project, and run the following command:

`$. npx eslint . --ext .js,.jsx,.ts,.tsx`

ESLint will lint all .js, .jsx, .ts, and .tsx files within the current folder, and output results to your terminal.

```js
module.exports = {
  extends: [
    'airbnb-typescript',
    'airbnb/hooks',
    'plugin:@typescript-eslint/recommended',
    'plugin:@typescript-eslint/recommended-requiring-type-checking',
  ],
};
```
