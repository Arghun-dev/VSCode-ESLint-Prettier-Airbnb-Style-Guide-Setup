# Add Eslint, Prettier and pre-commit checks

<hr />

## Install Eslint dependencied

`$. npm install eslint-config-airbnb-typescript --save-dev`
`$. npx install-peerdeps --dev eslint-config-airbnb`
`$. npm install eslint-plugin-jest @typescript-eslint/eslint-plugin --save-dev`

<hr />

## Install Prettier dependencies

`$. npm install --save-dev prettier @typescript-eslint/parser eslint-config-prettier eslint-plugin-prettier`

<hr />

## eslintrc.js

```js
module.exports = {
    extends: [
        "airbnb-typescript",
        "airbnb/hooks",
        "plugin:@typescript-eslint/recommended",
        "plugin:jest/recommended",
        "prettier",
        "prettier/react",
        "prettier/@typescript-eslint",
        "plugin:prettier/recommended"
    ],
    plugins: ["react", "prettier", "@typescript-eslint", "jest"],
    env: {
        browser: true,
        es6: true,
        jest: true
    },
    parserOptions: {
        project: './tsconfig.json'
    },
    rules: {
        'prettier/prettier': 'error'
    }
}
```

<hr />

## eslintignore

```js
node_modules/
build/
dist/
package-lock.json
```

<hr />

## scripts

```js
"scripts": {
    "lint": "eslint \"src/**/*.{ts, tsx}\"",
    "prettier:fix": "prettier --write \"src/**/*.{ts, tsx}\"",
    "prettier:check": "prettier \"src/**/*.{ts, tsx}\""
}
```
