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

`$. npm install typescript eslint prettier eslint-config-airbnb-typescript-prettier --save-dev`

in eslintrc:

`$. extends: "airbnb-typescript-prettier"`


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
