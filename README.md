vue3-cli
===

[TOC]

## 簡介

建立一個 vue3-cli 的 環境基底

## 安裝

1. 安裝 [node.js](https://nodejs.org/zh-tw/download/)
2. 透過 npm 安裝 yarn<br>
```shell
$ npm install --global yarn
```
檢查安裝
```shell
$ yarn --version
```
3. 安裝 vue-cli <br>

```shell
$ yarn global upgrade --latest @vue/cli
```

4. 建立專案 <br>

```shell
$ yarn create { project-name }
```

5. 設定<br>
```shell
Vue CLI v5.0.8
? Please pick a preset: (Use arrow keys)
  Default ([Vue 3] babel, eslint) // vue 3 預設安裝
  Default ([Vue 2] babel, eslint) // vue 2 預設安裝
>  Manually select features // 自定義安裝

```
選擇預設安裝項目
```shell
? Check the features needed for your project: (Press <space> to select, <a> to toggle all, <i> to invert selection, and <enter> to proceed)
>(*) Babel
 ( ) TypeScript
 ( ) Progressive Web App (PWA) Support
 (*) Router
 (*) Vuex
 ( ) CSS Pre-processors
 (*) Linter / Formatter
 ( ) Unit Testing
 ( ) E2E Testing
```
選擇版本
```shell
? Choose a version of Vue.js that you want to start the project with (Use arrow keys)
> 3.x
  2.x
```
預設router 使用history模式
```shell
?Use history mode for router? (Requires proper server setup for index fallback in production) (Y/n)  Y
```
選擇eslint規則模式
```shell
? Pick a linter / formatter config: 
  ESLint with error prevention only 
  ESLint + Airbnb config
> ESLint + Standard config
  ESLint + Prettier
```
選擇lint檢查程式碼的時機
```shell
? Pick additional lint features: (Press <space> to select, <a> to toggle all, <i> to invert selection, and <enter> to proceed)
>(*) Lint on save
 ( ) Lint and fix on commit
```
選擇儲存設定的方式
```shell
? Where do you prefer placing config for Babel, ESLint, etc.? (Use arrow keys)
> In dedicated config files
  In package.json
```
看你需不需要把這些設定儲存起來，先選擇(N)
```shell
? save this as a preset for future projects (y/n) N
```

## 調整eslint 自訂設置

進入專案資料夾，找尋.eslintrc.js
將內容覆蓋

~~調整為最嚴謹模式~~

```js
module.exports = {
  root: true,
  env: {
    node: true,
  },
  extends: ['plugin:vue/vue3-essential', '@vue/airbnb'],
  parserOptions: {
    parser: '@babel/eslint-parser',
  },
  rules: {
    'no-console': process.env.NODE_ENV === 'production' ? 'warn' : 'off',
    'no-debugger': process.env.NODE_ENV === 'production' ? 'warn' : 'off',
    'object-curly-newline': 'off',
    'import/no-dynamic-require': 'off',
    'global-require': 'off',
    'comma-dangle': 'off',
    'implicit-arrow-linebreak': 'off',
    'operator-linebreak': 'off',
    'arrow-body-style': 'off',
    'newline-per-chained-call': 'off',
  },
  overrides: [
    {
      files: ['**/__tests__/*.{j,t}s?(x)', '**/tests/unit/**/*.spec.{j,t}s?(x)'],
      env: {
        jest: true,
      },
    },
  ],
};
```


## 依賴

1. axios


## 開啟專案 

```
$ cd vue3-cli-base
yarn serve 
```

