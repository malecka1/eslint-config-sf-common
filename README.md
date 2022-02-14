# eslint-config-sf-common

[![npm version](https://badge.fury.io/js/eslint-config-sf-common.svg)](https://badge.fury.io/js/eslint-config-sf-common)

This package provides a complete set of ESLint rules for Salesforce projects with Aura and LWC support.

The package benefits from rules and configurations provided by the following packages:

* [Aura plugin by Salesforce](https://github.com/forcedotcom/eslint-plugin-aura)
* [LWC plugin by Salesforce](https://github.com/salesforce/eslint-plugin-lwc)
* [ESLint recommended configuration](https://github.com/eslint/eslint/blob/master/conf/eslint-recommended.js)
* [JSDoc](https://github.com/gajus/eslint-plugin-jsdoc)

## Usage
Example `.eslintrc.json` configuration file can look like this:
```json
{
  "overrides": [
    {
      "extends": [
        // https://github.com/forcedotcom/eslint-plugin-aura
        "plugin:@salesforce/eslint-plugin-aura/recommended",
        "eslint-config-sf-common"
      ],
      "files": [
        "src/**/aura/**"
      ],
      "plugins": [
        "@salesforce/eslint-plugin-aura"
      ],
      // override rules which are not applicable to Aura
      "rules": {
        "no-unused-expressions": "off",
        "object-shorthand": "off"
      }
    },
    {
      "extends": [
        // https://github.com/salesforce/eslint-config-lwc
        "@salesforce/eslint-config-lwc/recommended",
        "eslint-config-sf-common"
      ],
      "files": [
        "src/**/lwc/**"
      ]
    }
  ]
}
``` 

---

This project is not an official Salesforce product.
