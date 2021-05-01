# VSCode-ESLint-Prettier-Airbnb-Style-Guide-Setup-And-Typescript

`$. npm i -g eslint typescript`

**First install `ESlint` and `Prettier` extensions on your vscode**

**Set Format onSave**

Before Creating React App Do this: 

1. `$. npm iniy -y`
2. `$. npm i -D eslint prettier eslint-plugin-prettier eslint-config-prettier eslint-plugin-react eslint-config-react eslint-plugin-react-hooks`

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
