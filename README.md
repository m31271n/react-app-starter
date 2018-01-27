# react-app-starter

[![code style: prettier](https://img.shields.io/badge/code_style-prettier-ff69b4.svg)](https://github.com/prettier/prettier)
[![style: styled-components](https://img.shields.io/badge/style-%F0%9F%92%85%20styled--components-orange.svg?colorB=daa357&colorA=db748e)](https://github.com/styled-components/styled-components)

<!-- start: markdown-toc -->

* [Preface](#preface)
* [Runtime Enhancement](#runtime-enhancement)
  * [Browser Polyfills](#browser-polyfills)
* [React Enhancement](#react-enhancement)
  * [Typechecking](#typechecking)
  * [Router](#router)
  * [State Management](#state-management)
  * [Stylesheets](#stylesheets)
  * [Static Assets](#static-assets)
* [QA](#qa)
  * [Linter](#linter)
    * [JS Linter](#js-linter)
    * [CSS Linter](#css-linter)
  * [Auto Formatting](#auto-formatting)
  * [Static Type checking (TODO)](#static-type-checking-todo)
  * [Test (TODO)](#test-todo)
* [API Request](#api-request)
* [Environment Variables](#environment-variables)
* [Deployment](#deployment)
* [SEO](#seo)
* [LICENSE](#license)

<!-- end: markdown-toc -->

## Preface

> CRA is short for [Creat React App](https://github.com/facebook/create-react-app).

I wanna tweak CRA app's webpack configs without [ejecting](https://github.com/facebook/create-react-app/blob/master/packages/react-scripts/template/README.md#npm-run-eject) or forking the [react-scripts](https://www.npmjs.com/package/react-scripts). Why? Because it will make me lose ability to get upgrade provided by react-scripts. So, I use a mild method called [react-app-rewired](https://github.com/timarney/react-app-rewired) to achieve this.

Related packages:

* `react-app-rewired`

## Runtime Enhancement

### Browser Polyfills

* [Promise](https://github.com/then/promise)
* [fetch() API](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API)

## React Enhancement

### Typechecking

Related packages:

* `prop-types`

Read more:

* [Typechecking With PropTypes](https://reactjs.org/docs/typechecking-with-proptypes.html)

### Router

Related packages:

* `react-router`
* `react-router-dom`

Read more:

* [Code Splitting With react-router](https://serverless-stack.com/chapters/code-splitting-in-create-react-app.html)
* [Configure production server to support client-side routing](https://github.com/facebook/create-react-app/blob/master/packages/react-scripts/template/README.md#serving-apps-with-client-side-routing)

### State Management

Use mobx in strict-mode for state management.

Related packages:

* `react-app-rewire-mobx`
* `mobx`

### Stylesheets

* CSS / styled-components / polished / autoprefixer are supported.

Related packages:

* `react-app-rewire-styled-components`
* `stylted-components`
* `react-app-rewire-polished`
* `polished`

### Static Assets

Images / Fonts / Other files are supported.

* Images types: `bmp`, `gif`, `jpg`, `jpeg`, `png`, `svg`

## QA

### Linter

Linter have 2 categories of rules:

* Formatting rules.
* Code-quality rules.

#### JS Linter

CRA intentionally provides a set of ESLint rules called "react-app" - includes formatting rules and code-quality rules.

But, in the aspect of formatting rules, I prefer [prettier](https://prettier.io/) personally. So, I extend `eslint-config-react-app` with `eslint-plugin-prettier`.

Related packages:

* `react-app-rewire-eslint`
* `eslint`
* `eslint-config-react-app`

  * `babel-eslint`
  * `eslint-plugin-flowtype`
  * `eslint-plugin-import`
  * `eslint-plugin-jsx-a11y`
  * `eslint-plugin-react`

* `eslint-plugin-prettier`
  * `prettier`
  * `eslint-config-prettier`

#### CSS Linter

Related packages:

* `stylelint`
* `stylelint-config-standard`
* `stylelint-config-prettier`

### Auto Formatting

Related packages:

* `husky` - helper for githook defined in npm scripts.
* `lint-staged` - command runner on staged files in git.
* `prettier` - code formatter.

The auto formatting steps are:

1. `husky` runs githook.
2. `lint-staged` runs as a githook.
3. `prettier` runs as a step in `lint-staged`'s configs.

### Static Type checking (TODO)

* [Adding Flow](https://github.com/facebook/create-react-app/blob/master/packages/react-scripts/template/README.md#adding-flow)

### Test (TODO)

* [Running Tests - Doc from CRA](https://github.com/facebook/create-react-app/blob/master/packages/react-scripts/template/README.md#running-tests)

## API Request

* [AJAX and APIs - Doc from React](https://reactjs.org/docs/faq-ajax.html)

## Environment Variables

`NODE_ENV` is provided by default. When you run `npm start`, it is always equal to 'development', when you run `npm test` it is always equal to 'test', and when you run `npm run build` to make a production bundle, it is always equal to 'production'. It is read-only for preventing developers from accidentally deploying a slow development build to production.

And, you can create custom enviroment variables beginning with `REACT_APP_`. Any other enviroment variables will be ignored.

All the environment variables are accessed by `process.env` in js files or by `%XXX%` in `public/index.html`.

## Deployment

* [Deployment - Doc from CRA](https://github.com/facebook/create-react-app/blob/master/packages/react-scripts/template/README.md#deployment)

## SEO

* [How to build a SEO-friendly React blog with an API-based CMS](https://hackernoon.com/react-js-cms-blog-tutorial-e090c699845b)

## LICENSE

MIT
