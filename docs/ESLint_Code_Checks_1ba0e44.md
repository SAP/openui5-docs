<!-- loio1ba0e44f1036439b95f25527664f14f7 -->

| loio |
| -----|
| 1ba0e44f1036439b95f25527664f14f7 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/1ba0e44f1036439b95f25527664f14f7) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/1ba0e44f1036439b95f25527664f14f7)</div>

## ESLint Code Checks

OpenUI5 uses ESLint to check JavaScript sources.

The following tables show the ESLint rules that should be enabled for the OpenUI5 projects.

***

### Rule Sets

Possible Errors<a name="loio1ba0e44f1036439b95f25527664f14f7__table_i4g_r3n_np"/>

|Rule|ESLint default|Core|Comment|
|----|--------------|----|-------|
|`no-cond-assign`|error|error| |
|`no-console`|error|error| |
|`no-constant-condition`|error|error| |
|`no-comma-dangle`|error|**error/warning**|can be set to warning if lib only supports IE9|
|`no-control-regex`|error|error| |
|`no-debugger`|error|error| |
|`no-dupe-keys`|error|error| |
|`no-empty`|error|error| |
|`no-empty-class`|error|error| |
|`no-ex-assign`|error|error| |
|`no-extra-boolean-cast`|error|**warning**| |
|`no-extra-parens`|off|off| |
|`no-extra-semi`|error|error| |
|`no-func-assign`|error|error| |
|`no-inner-declarations`|error|error| |
|`no-invalid-regexp`|error|error| |
|`no-negated-in-lhs`|error|error| |
|`no-obj-calls`|error|error| |
|`no-regex-spaces`|error|error| |
|`no-sparse-arrays`|error|error| |
|`no-unreachable`|error|error| |
|`use-isnan`|error|error| |
|`valid-jsdoc`|off|**warning**|`requireReturn` = false|
|`valid-typeof`|error|error| |

Best Practices<a name="loio1ba0e44f1036439b95f25527664f14f7__table_gwc_t3n_np"/>

|Rule|ESLint default|Core|Comment|
|----|--------------|----|-------|
|`block-scoped-var`|off|**error**|currently only warning because of wrong behaviour in switch statement|
|`complexity`|off|off| |
|`consistent-return`|error|**warning**| |
|`curly`|error|error| |
|`default-case`|off|**warning**| |
|`dot-notation`|error|**off**| |
|`eqeqeq`|error|**warning**|`smart`|
|`guard-for-in`|off|**error**| |
|`no-alert`|error|error| |
|`no-caller`|error|error| |
|`no-div-regex`|off|**error**| |
|`no-else-return`|off|off| |
|`no-empty-label`|error|error| |
|`no-eq-null`|off|off| |
|`no-eval`|error|error| |
|`no-extend-native`|error|error| |
|`no-fallthrough`|error|error| |
|`no-floating-decimal`|off|**error**| |
|`no-implied-eval`|error|error| |
|`no-labels`|error|error| |
|`no-iterator`|error|error| |
|`no-lone-blocks`|error|error| |
|`no-loop-func`|error|error| |
|`no-multi-str`|error|error| |
|`no-native-reassign`|error|error| |
|`no-new`|error|error| |
|`no-new-func`|error|error| |
|`no-new-wrappers`|error|**warning**| |
|`no-octal`|error|error| |
|`no-octal-escape`|error|error| |
|`no-proto`|error|error| |
|`no-redeclare`|error|**warning**| |
|`no-return-assign`|error|error| |
|`no-script-url`|error|error| |
|`no-self-compare`|off|**error**| |
|`no-sequences`|error|error| |
|`no-unused-expressions`|error|**warning**| |
|`no-warning-comments`|off|**warning**| |
|`no-with`|error|error| |
|`radix`|off|**error**| |
|`wrap-life`|off|**error**|any|
|`yoda`|error|error| |

Strict Mode<a name="loio1ba0e44f1036439b95f25527664f14f7__table_vxj_v3n_np"/>

|Rule|ESLint defaul|Core|
|----|-------------|----|
|`global-strict`|off|**error**|
|`no-extra-strict`|error|error|
|`strict`|error|**warning**|

Variables<a name="loio1ba0e44f1036439b95f25527664f14f7__table_el2_x3n_np"/>

|Rule|ESLint default|Core|Comment|
|----|--------------|----|-------|
|`no-catch-shadow`|error|error| |
|`no-delete-var`|error|error| |
|`no-label-var`|error|error| |
|`no-shadow`|error|error| |
|`no-shadow-restricted-names`|error|error| |
|`no-undef`|error|error| |
|`no-undefined`|off|off| |
|`no-undef-init`|error|error| |
|`no-unused-vars`|error|error|`vars = all`, `args` = none|
|`no-use-before-define`|error|**warning**| |

Node.js<a name="loio1ba0e44f1036439b95f25527664f14f7__table_yy2_bjn_np"/>

|Rule|ESLint default|Core|
|----|--------------|----|
|`handle-callback-err`|off|off|
|`no-mixed-requires`|off|off|
|`no-new-require`|off|off|
|`no-path-concat`|off|off|
|`no-process-exit`|off|off|
|`no-restricted-modules`|off|off|
|`no-sync`|off|off|

Stylistic<a name="loio1ba0e44f1036439b95f25527664f14f7__table_d5f_2jn_np"/>

|Rule|ESLint default|Core|Comment|
|----|--------------|----|-------|
|`brace-style`|off|**error**|`singleLine = false` |
|`camelcase`|error|warning| |
|`consistent-this`|off|**error**|`that`|
|`eol-last`|error|**off**| |
|`func-names`|off|off| |
|`func-style`|off|off| |
|`new-cap`|error|**warning**| |
|`new-parens`|error|error| |
|`no-nested-ternary`|off|**error**| |
|`no-array-constructor`|error|error| |
|`no-lonely-if`|off|**error**| |
|`no-new-object`|error|error| |
|`no-spaced-func`|error|error| |
|`no-space-before-semi`|error|error| |
|`no-ternary`|off|off| |
|`no-trailing-spaces`|error|**off**|error, but too many places to change|
|`no-underscore-dangle`|error|**off**| |
|`no-wrap-func`|error|error| |
|`no-mixed-spaces-and-tabs`|error|error|`smart`|
|`quotes`|off|off| |
|`quote-props`|off|off| |
|`semi`|error|error| |
|`sort-vars`|off|off| |
|`space-after-keywords`|off|**error**|`always`|
|`space-in-brackets`|off|off| |
|`space-infix-ops`|error|error| |
|`space-return-throw-case`|error|error| |
|`space-unary-word-ops`|off|**error**| |
|`max-nested-callbacks`|off|**warning**|`3`|
|`one-var`|off|off| |
|`wrap-regex`|off|off| |

Legacy<a name="loio1ba0e44f1036439b95f25527664f14f7__table_ung_gjn_np"/>

|Rule|ESLint default|SAPUI5 Core|
|----|--------------|-----------|
|`max-depth`|off|off|
|`max-len`|off|off|
|`max-params`|off|off|
|`max-statements`|off|off|
|`no-bitwise`|off|off|
|`no-plus`|off|off|

For more information about the rules, see the rules documentation provided on [http://eslint.org](http://eslint.org).

