# eslint-config-dhi

[![npm version](https://badge.fury.io/js/eslint-config-dhi.svg)](http://badge.fury.io/js/eslint-config-dhi)

This package provides DHI's .eslintrc as an extensible shared config.

It's a fork of Airbnb's eslint config, with DHI flavor.
 

### Getting started
Our default export contains all of our ESLint rules, including ECMAScript 6+.
 
Add `{ "extends": "dhi" }` to your .eslintrc.


### Running tests
```
npm run test
```


### Modifying rules
Make a pull request with the rule that should be modified and why.


### Improving this config
Consider adding test cases if you're making complicated rules changes, like anything involving regexes. Perhaps in a distant future, we could use literate programming to structure our README as test cases for our .eslintrc?
