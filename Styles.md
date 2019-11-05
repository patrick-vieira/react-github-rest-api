
# Styleguide setup.

## Install ESLint extension for VSCode

>https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint

## Install dependencies

install eslint:
> yarn add eslint -D

install prettier:
> yarn add prettier eslint-config-prettier eslint-plugin-prettier babel-eslint -D

## configure .eslintrc
> yarn eslint --init

    ? How would you like to use ESLint?
    > To check syntax, find problems, and enforce code style

    ? What type of modules does your project use?
    > JavaScript modules (import/export)

    ? Which framework does your project use?
    > React

    ? Does your project use TypeScript?
    > No

    ? Where does your code run?
    > Browser

    ? How would you like to define a style for your project?
    > Use a popular style guide

    ? Which style guide do you want to follow?
    > Airbnb (https://github.com/airbnb/javascript)

    ? What format do you want your config file to be in?
    > JavaScript

- on root folder will be created a file called ``.eslintrc``, i will make some changes to use prettier and babel-parser.

````js
module.exports = {
  env: {
    browser: true,
    es6: true,
  },
  extends: [
    'airbnb',
    'prettier',
    'prettier/react'
  ],
  globals: {
    Atomics: 'readonly',
    SharedArrayBuffer: 'readonly',
  },
  parser: 'babel-eslint',
  parserOptions: {
    ecmaFeatures: {
      jsx: true,
    },
    ecmaVersion: 2018,
    sourceType: 'module',
  },
  plugins: [
    'react',
    'prettier'
  ],
  rules: {
    'prettier/prettier': 'error',
    'react/jsx-filename-extension': [
      'warn',
      { extensions: ['.jsx', '.js']}
    ],
    'import/prefer-default-export': 'off'
  },
};
````

## Configure .prettierrc

On root folder create a file called ``.prettierrc``

````js
{
  "singleQuote": true,
  "trailingComma": "es5"
}
````


## Configure .editorconfig

````js
root = true

[*]
end_of_line = lf
indent_style = space
indent_size = 2
charset = utf-8
trim_trailing_whitespace = true
insert_final_newline = true
````




