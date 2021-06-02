# denizenapp/eslint-config-denizenapp

Shared ESLint config for Denizenapp projects.

This is meant to be used alongside Prettier (via [`denizenapp/prettier-config-denizenapp`](https://github.com/denizenapp/prettier-config-denizenapp)).

## Setup

1. Remove existing `.eslintrc.*` file, if present.
1. Install `eslint` and this config directly from Github (for now).

    ```
    npm install -D eslint denizenapp/eslint-config-denizenapp#main
    ```

1. Add the following to `package.json`:

    ```
    "eslintConfig": {
        "extends": "eslint-config-denizenapp"
    }
    ```

## Usage with Prettier and `prettier-config-denizenapp`

1. Set up Prettier and [`denizenapp/prettier-config-denizenapp`](https://github.com/denizenapp/prettier-config-denizenapp).
1. When using with Prettier and `denizenapp/prettier-config-denizenapp`, ESLint should run first. Set up your scripts in `package.json` like this:

    ```json
      "scripts": {
    	"lint": "eslint --ignore-path .gitignore . && prettier --check {,*/**/}*.{js,css,json,md}",
    	"format": "eslint --ignore-path .gitignore . --fix && prettier --write {,*/**/}*.{js,css,json,md}",
      }
    ```

1. Then use the following commands:
    - `npm run lint` to view ESLint and Prettier errors and warnings.
    - `npm run format` to attempt to autofix and autoformat code.
