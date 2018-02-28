# eslint-config-dhi

[![npm version](https://badge.fury.io/js/eslint-config-dhi.svg)](http://badge.fury.io/js/eslint-config-dhi)

This package provides DHI's .eslintrc as an extensible shared config.

It's a fork of Airbnb's eslint config, with DHI flavor.


### Getting started
Our default export contains all of our ESLint rules, including ECMAScript 6+.

Add this package as a dependency to your application:
```bash
npm i eslint-config-dhi -D # OR yarn add eslint-config-dhi -D
```

Add `{ "extends": ["eslint-config-dhi"] }` to your `.eslintrc.js`.


### Advanced

#### Using Babel
If your project uses ES6 or relies on babel features, the config should look something like this:

```javascript
module.exports = {
  "root": true,
  "parser": "babel-eslint",
  "extends": ["dhi"],
  "parserOptions": {
    "ecmaVersion": 8,
    "sourceType": "module",
    "ecmaFeatures": {
      "jsx": true,
      "experimentalObjectRestSpread": true
    }
  },

  "globals": {
    Polymer: true,
    Promise: true
  }
};
```

> Remember to install babel & babel-eslint. Using `@babel/preset-env` is recommended.

#### Using debugger in dev mode
If you want to use debugger statements during dev, you can turn it on in your .eslintrc.js file:

```javascript
...
  "rules": {
    "no-debugger": process.env.NODE_ENV === "production" ? 2: 0 // Allow debugger during development
  }
...
```

#### Using JSDoc
For projects that use JSDoc for documenting code, it might come in handy to use `eslint-plugin-jsdoc`. The recommended configuration to add to your project's .eslintrc is:

```javascript
  rules: {
    "jsdoc/check-param-names": 1,
    "jsdoc/check-types": 1,
    "jsdoc/newline-after-description": 1,
    "jsdoc/require-description-complete-sentence": 1,
    "jsdoc/require-param": 1,
    "jsdoc/require-param-name": 1,
    "jsdoc/require-param-type": 1,
    "jsdoc/require-returns-description": 1,
    "jsdoc/require-returns-type": 1
  },

  plugins: ['jsdoc']
```



### Running tests
```
npm run test
```


### Modifying rules
Make a pull request with the rule that should be modified and why.


### Improving this config
Consider adding test cases if you're making complicated rules changes, like anything involving regexes. Perhaps in a distant future, we could use literate programming to structure our README as test cases for our .eslintrc?
