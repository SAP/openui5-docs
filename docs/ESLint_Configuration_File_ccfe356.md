| loio |
| -----|
| ccfe35638f1d46e2bbcf06fa60ccc6ef |

<div id="loio">

view on: [help.sap.com](https://help.sap.com/viewer/DRAFT/3237636b137e43519a20ad5513c49ccb/latest/en-US/ccfe35638f1d46e2bbcf06fa60ccc6ef.html) | [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/ccfe35638f1d46e2bbcf06fa60ccc6ef) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/ccfe35638f1d46e2bbcf06fa60ccc6ef)</div>
<!-- loioccfe35638f1d46e2bbcf06fa60ccc6ef -->

## ESLint Configuration File

Content of the ESLint configuration file

```lang-js

{
	"env": {
		"browser": true
	},
	"globals": {
		"sap": true,
		"jQuery": true
	},
	"rules": {
		"block-scoped-var": 1,
		"brace-style": [2, "1tbs", { "allowSingleLine": true }],
		"consistent-this": 2,
		"global-strict": 2,
		"no-div-regex": 2,
		"no-floating-decimal": 2,
		"no-self-compare": 2,
		"no-mixed-spaces-and-tabs": [2, true],
		"no-nested-ternary": 2,
		"no-unused-vars": [2, {"vars":"all", "args":"none"}],
		"radix": 2,
		"space-after-keywords": [2, "always"],
		"space-unary-word-ops": 2,
		"wrap-iife": [2, "any"],

		"camelcase": 1,
		"consistent-return": 1,
		"max-nested-callbacks": [1, 3],
		"new-cap": 1,
		"no-extra-boolean-cast": 1,
		"no-lonely-if": 1,
		"no-new": 1,
		"no-new-wrappers": 1,
		"no-redeclare": 1,
		"no-unused-expressions": 1,
		"no-use-before-define": [1, "nofunc"],
		"no-warning-comments": 1,
		"strict": 1,
		"valid-jsdoc": [1, {
			"requireReturn": false
		}],
		"default-case": 1,

		"dot-notation": 0,
		"eol-last": 0,
		"eqeqeq": 0,
		"no-trailing-spaces": 0,
		"no-underscore-dangle": 0,
		"quotes": 0
	}
}

```

