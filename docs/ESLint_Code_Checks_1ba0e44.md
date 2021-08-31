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

<a name="loio1ba0e44f1036439b95f25527664f14f7__table_i4g_r3n_np"/>Possible Errors


<table>
<tr>
<th>

Rule



</th>
<th>

ESLint default



</th>
<th>

Core



</th>
<th>

Comment



</th>
</tr>
<tr>
<td>

`no-cond-assign`



</td>
<td>

error



</td>
<td>

error



</td>
<td>

 



</td>
</tr>
<tr>
<td>

`no-console`



</td>
<td>

error



</td>
<td>

error



</td>
<td>

 



</td>
</tr>
<tr>
<td>

`no-constant-condition`



</td>
<td>

error



</td>
<td>

error



</td>
<td>

 



</td>
</tr>
<tr>
<td>

`no-comma-dangle`



</td>
<td>

error



</td>
<td>

**error/warning**



</td>
<td>

can be set to warning if lib only supports IE9



</td>
</tr>
<tr>
<td>

`no-control-regex`



</td>
<td>

error



</td>
<td>

error



</td>
<td>

 



</td>
</tr>
<tr>
<td>

`no-debugger`



</td>
<td>

error



</td>
<td>

error



</td>
<td>

 



</td>
</tr>
<tr>
<td>

`no-dupe-keys`



</td>
<td>

error



</td>
<td>

error



</td>
<td>

 



</td>
</tr>
<tr>
<td>

`no-empty`



</td>
<td>

error



</td>
<td>

error



</td>
<td>

 



</td>
</tr>
<tr>
<td>

`no-empty-class`



</td>
<td>

error



</td>
<td>

error



</td>
<td>

 



</td>
</tr>
<tr>
<td>

`no-ex-assign`



</td>
<td>

error



</td>
<td>

error



</td>
<td>

 



</td>
</tr>
<tr>
<td>

`no-extra-boolean-cast`



</td>
<td>

error



</td>
<td>

**warning**



</td>
<td>

 



</td>
</tr>
<tr>
<td>

`no-extra-parens`



</td>
<td>

off



</td>
<td>

off



</td>
<td>

 



</td>
</tr>
<tr>
<td>

`no-extra-semi`



</td>
<td>

error



</td>
<td>

error



</td>
<td>

 



</td>
</tr>
<tr>
<td>

`no-func-assign`



</td>
<td>

error



</td>
<td>

error



</td>
<td>

 



</td>
</tr>
<tr>
<td>

`no-inner-declarations`



</td>
<td>

error



</td>
<td>

error



</td>
<td>

 



</td>
</tr>
<tr>
<td>

`no-invalid-regexp`



</td>
<td>

error



</td>
<td>

error



</td>
<td>

 



</td>
</tr>
<tr>
<td>

`no-negated-in-lhs`



</td>
<td>

error



</td>
<td>

error



</td>
<td>

 



</td>
</tr>
<tr>
<td>

`no-obj-calls`



</td>
<td>

error



</td>
<td>

error



</td>
<td>

 



</td>
</tr>
<tr>
<td>

`no-regex-spaces`



</td>
<td>

error



</td>
<td>

error



</td>
<td>

 



</td>
</tr>
<tr>
<td>

`no-sparse-arrays`



</td>
<td>

error



</td>
<td>

error



</td>
<td>

 



</td>
</tr>
<tr>
<td>

`no-unreachable`



</td>
<td>

error



</td>
<td>

error



</td>
<td>

 



</td>
</tr>
<tr>
<td>

`use-isnan`



</td>
<td>

error



</td>
<td>

error



</td>
<td>

 



</td>
</tr>
<tr>
<td>

`valid-jsdoc`



</td>
<td>

off



</td>
<td>

**warning**



</td>
<td>

`requireReturn` = false



</td>
</tr>
<tr>
<td>

`valid-typeof`



</td>
<td>

error



</td>
<td>

error



</td>
<td>

 



</td>
</tr>
</table>

<a name="loio1ba0e44f1036439b95f25527664f14f7__table_gwc_t3n_np"/>Best Practices


<table>
<tr>
<th>

Rule



</th>
<th>

ESLint default



</th>
<th>

Core



</th>
<th>

Comment



</th>
</tr>
<tr>
<td>

`block-scoped-var`



</td>
<td>

off



</td>
<td>

**error**



</td>
<td>

currently only warning because of wrong behaviour in switch statement



</td>
</tr>
<tr>
<td>

`complexity`



</td>
<td>

off



</td>
<td>

off



</td>
<td>

 



</td>
</tr>
<tr>
<td>

`consistent-return`



</td>
<td>

error



</td>
<td>

**warning**



</td>
<td>

 



</td>
</tr>
<tr>
<td>

`curly`



</td>
<td>

error



</td>
<td>

error



</td>
<td>

 



</td>
</tr>
<tr>
<td>

`default-case`



</td>
<td>

off



</td>
<td>

**warning**



</td>
<td>

 



</td>
</tr>
<tr>
<td>

`dot-notation`



</td>
<td>

error



</td>
<td>

**off**



</td>
<td>

 



</td>
</tr>
<tr>
<td>

`eqeqeq`



</td>
<td>

error



</td>
<td>

**warning**



</td>
<td>

`smart`



</td>
</tr>
<tr>
<td>

`guard-for-in`



</td>
<td>

off



</td>
<td>

**error**



</td>
<td>

 



</td>
</tr>
<tr>
<td>

`no-alert`



</td>
<td>

error



</td>
<td>

error



</td>
<td>

 



</td>
</tr>
<tr>
<td>

`no-caller`



</td>
<td>

error



</td>
<td>

error



</td>
<td>

 



</td>
</tr>
<tr>
<td>

`no-div-regex`



</td>
<td>

off



</td>
<td>

**error**



</td>
<td>

 



</td>
</tr>
<tr>
<td>

`no-else-return`



</td>
<td>

off



</td>
<td>

off



</td>
<td>

 



</td>
</tr>
<tr>
<td>

`no-empty-label`



</td>
<td>

error



</td>
<td>

error



</td>
<td>

 



</td>
</tr>
<tr>
<td>

`no-eq-null`



</td>
<td>

off



</td>
<td>

off



</td>
<td>

 



</td>
</tr>
<tr>
<td>

`no-eval`



</td>
<td>

error



</td>
<td>

error



</td>
<td>

 



</td>
</tr>
<tr>
<td>

`no-extend-native`



</td>
<td>

error



</td>
<td>

error



</td>
<td>

 



</td>
</tr>
<tr>
<td>

`no-fallthrough`



</td>
<td>

error



</td>
<td>

error



</td>
<td>

 



</td>
</tr>
<tr>
<td>

`no-floating-decimal`



</td>
<td>

off



</td>
<td>

**error**



</td>
<td>

 



</td>
</tr>
<tr>
<td>

`no-implied-eval`



</td>
<td>

error



</td>
<td>

error



</td>
<td>

 



</td>
</tr>
<tr>
<td>

`no-labels`



</td>
<td>

error



</td>
<td>

error



</td>
<td>

 



</td>
</tr>
<tr>
<td>

`no-iterator`



</td>
<td>

error



</td>
<td>

error



</td>
<td>

 



</td>
</tr>
<tr>
<td>

`no-lone-blocks`



</td>
<td>

error



</td>
<td>

error



</td>
<td>

 



</td>
</tr>
<tr>
<td>

`no-loop-func`



</td>
<td>

error



</td>
<td>

error



</td>
<td>

 



</td>
</tr>
<tr>
<td>

`no-multi-str`



</td>
<td>

error



</td>
<td>

error



</td>
<td>

 



</td>
</tr>
<tr>
<td>

`no-native-reassign`



</td>
<td>

error



</td>
<td>

error



</td>
<td>

 



</td>
</tr>
<tr>
<td>

`no-new`



</td>
<td>

error



</td>
<td>

error



</td>
<td>

 



</td>
</tr>
<tr>
<td>

`no-new-func`



</td>
<td>

error



</td>
<td>

error



</td>
<td>

 



</td>
</tr>
<tr>
<td>

`no-new-wrappers`



</td>
<td>

error



</td>
<td>

**warning**



</td>
<td>

 



</td>
</tr>
<tr>
<td>

`no-octal`



</td>
<td>

error



</td>
<td>

error



</td>
<td>

 



</td>
</tr>
<tr>
<td>

`no-octal-escape`



</td>
<td>

error



</td>
<td>

error



</td>
<td>

 



</td>
</tr>
<tr>
<td>

`no-proto`



</td>
<td>

error



</td>
<td>

error



</td>
<td>

 



</td>
</tr>
<tr>
<td>

`no-redeclare`



</td>
<td>

error



</td>
<td>

**warning**



</td>
<td>

 



</td>
</tr>
<tr>
<td>

`no-return-assign`



</td>
<td>

error



</td>
<td>

error



</td>
<td>

 



</td>
</tr>
<tr>
<td>

`no-script-url`



</td>
<td>

error



</td>
<td>

error



</td>
<td>

 



</td>
</tr>
<tr>
<td>

`no-self-compare`



</td>
<td>

off



</td>
<td>

**error**



</td>
<td>

 



</td>
</tr>
<tr>
<td>

`no-sequences`



</td>
<td>

error



</td>
<td>

error



</td>
<td>

 



</td>
</tr>
<tr>
<td>

`no-unused-expressions`



</td>
<td>

error



</td>
<td>

**warning**



</td>
<td>

 



</td>
</tr>
<tr>
<td>

`no-warning-comments`



</td>
<td>

off



</td>
<td>

**warning**



</td>
<td>

 



</td>
</tr>
<tr>
<td>

`no-with`



</td>
<td>

error



</td>
<td>

error



</td>
<td>

 



</td>
</tr>
<tr>
<td>

`radix`



</td>
<td>

off



</td>
<td>

**error**



</td>
<td>

 



</td>
</tr>
<tr>
<td>

`wrap-life`



</td>
<td>

off



</td>
<td>

**error**



</td>
<td>

any



</td>
</tr>
<tr>
<td>

`yoda`



</td>
<td>

error



</td>
<td>

error



</td>
<td>

 



</td>
</tr>
</table>

<a name="loio1ba0e44f1036439b95f25527664f14f7__table_vxj_v3n_np"/>Strict Mode


<table>
<tr>
<th>

Rule



</th>
<th>

ESLint default



</th>
<th>

Core



</th>
</tr>
<tr>
<td>

`no-extra-strict`



</td>
<td>

error



</td>
<td>

error



</td>
</tr>
<tr>
<td>

`strict`



</td>
<td>

off



</td>
<td>

**error**



</td>
</tr>
</table>

<a name="loio1ba0e44f1036439b95f25527664f14f7__table_el2_x3n_np"/>Variables


<table>
<tr>
<th>

Rule



</th>
<th>

ESLint default



</th>
<th>

Core



</th>
<th>

Comment



</th>
</tr>
<tr>
<td>

`no-catch-shadow`



</td>
<td>

error



</td>
<td>

error



</td>
<td>

 



</td>
</tr>
<tr>
<td>

`no-delete-var`



</td>
<td>

error



</td>
<td>

error



</td>
<td>

 



</td>
</tr>
<tr>
<td>

`no-label-var`



</td>
<td>

error



</td>
<td>

error



</td>
<td>

 



</td>
</tr>
<tr>
<td>

`no-shadow`



</td>
<td>

error



</td>
<td>

error



</td>
<td>

 



</td>
</tr>
<tr>
<td>

`no-shadow-restricted-names`



</td>
<td>

error



</td>
<td>

error



</td>
<td>

 



</td>
</tr>
<tr>
<td>

`no-undef`



</td>
<td>

error



</td>
<td>

error



</td>
<td>

 



</td>
</tr>
<tr>
<td>

`no-undefined`



</td>
<td>

off



</td>
<td>

off



</td>
<td>

 



</td>
</tr>
<tr>
<td>

`no-undef-init`



</td>
<td>

error



</td>
<td>

error



</td>
<td>

 



</td>
</tr>
<tr>
<td>

`no-unused-vars`



</td>
<td>

error



</td>
<td>

error



</td>
<td>

`vars = all`, `args` = none



</td>
</tr>
<tr>
<td>

`no-use-before-define`



</td>
<td>

error



</td>
<td>

**warning**



</td>
<td>

 



</td>
</tr>
</table>

<a name="loio1ba0e44f1036439b95f25527664f14f7__table_yy2_bjn_np"/>Node.js


<table>
<tr>
<th>

Rule



</th>
<th>

ESLint default



</th>
<th>

Core



</th>
</tr>
<tr>
<td>

`handle-callback-err`



</td>
<td>

off



</td>
<td>

off



</td>
</tr>
<tr>
<td>

`no-mixed-requires`



</td>
<td>

off



</td>
<td>

off



</td>
</tr>
<tr>
<td>

`no-new-require`



</td>
<td>

off



</td>
<td>

off



</td>
</tr>
<tr>
<td>

`no-path-concat`



</td>
<td>

off



</td>
<td>

off



</td>
</tr>
<tr>
<td>

`no-process-exit`



</td>
<td>

off



</td>
<td>

off



</td>
</tr>
<tr>
<td>

`no-restricted-modules`



</td>
<td>

off



</td>
<td>

off



</td>
</tr>
<tr>
<td>

`no-sync`



</td>
<td>

off



</td>
<td>

off



</td>
</tr>
</table>

<a name="loio1ba0e44f1036439b95f25527664f14f7__table_d5f_2jn_np"/>Stylistic


<table>
<tr>
<th>

Rule



</th>
<th>

ESLint default



</th>
<th>

Core



</th>
<th>

Comment



</th>
</tr>
<tr>
<td>

`brace-style`



</td>
<td>

off



</td>
<td>

**error**



</td>
<td>

`singleLine = false` 



</td>
</tr>
<tr>
<td>

`camelcase`



</td>
<td>

error



</td>
<td>

warning



</td>
<td>

 



</td>
</tr>
<tr>
<td>

`consistent-this`



</td>
<td>

off



</td>
<td>

**error**



</td>
<td>

`that`



</td>
</tr>
<tr>
<td>

`eol-last`



</td>
<td>

error



</td>
<td>

**off**



</td>
<td>

 



</td>
</tr>
<tr>
<td>

`func-names`



</td>
<td>

off



</td>
<td>

off



</td>
<td>

 



</td>
</tr>
<tr>
<td>

`func-style`



</td>
<td>

off



</td>
<td>

off



</td>
<td>

 



</td>
</tr>
<tr>
<td>

`new-cap`



</td>
<td>

error



</td>
<td>

**warning**



</td>
<td>

 



</td>
</tr>
<tr>
<td>

`new-parens`



</td>
<td>

error



</td>
<td>

error



</td>
<td>

 



</td>
</tr>
<tr>
<td>

`no-nested-ternary`



</td>
<td>

off



</td>
<td>

**error**



</td>
<td>

 



</td>
</tr>
<tr>
<td>

`no-array-constructor`



</td>
<td>

error



</td>
<td>

error



</td>
<td>

 



</td>
</tr>
<tr>
<td>

`no-lonely-if`



</td>
<td>

off



</td>
<td>

**error**



</td>
<td>

 



</td>
</tr>
<tr>
<td>

`no-new-object`



</td>
<td>

error



</td>
<td>

error



</td>
<td>

 



</td>
</tr>
<tr>
<td>

`no-spaced-func`



</td>
<td>

error



</td>
<td>

error



</td>
<td>

 



</td>
</tr>
<tr>
<td>

`no-space-before-semi`



</td>
<td>

error



</td>
<td>

error



</td>
<td>

 



</td>
</tr>
<tr>
<td>

`no-ternary`



</td>
<td>

off



</td>
<td>

off



</td>
<td>

 



</td>
</tr>
<tr>
<td>

`no-trailing-spaces`



</td>
<td>

error



</td>
<td>

**off**



</td>
<td>

error, but too many places to change



</td>
</tr>
<tr>
<td>

`no-underscore-dangle`



</td>
<td>

error



</td>
<td>

**off**



</td>
<td>

 



</td>
</tr>
<tr>
<td>

`no-wrap-func`



</td>
<td>

error



</td>
<td>

error



</td>
<td>

 



</td>
</tr>
<tr>
<td>

`no-mixed-spaces-and-tabs`



</td>
<td>

error



</td>
<td>

error



</td>
<td>

`smart`



</td>
</tr>
<tr>
<td>

`quotes`



</td>
<td>

off



</td>
<td>

off



</td>
<td>

 



</td>
</tr>
<tr>
<td>

`quote-props`



</td>
<td>

off



</td>
<td>

off



</td>
<td>

 



</td>
</tr>
<tr>
<td>

`semi`



</td>
<td>

error



</td>
<td>

error



</td>
<td>

 



</td>
</tr>
<tr>
<td>

`sort-vars`



</td>
<td>

off



</td>
<td>

off



</td>
<td>

 



</td>
</tr>
<tr>
<td>

`keyword-spacing`



</td>
<td>

off



</td>
<td>

**error**



</td>
<td>

`“after”: true`



</td>
</tr>
<tr>
<td>

`space-in-brackets`



</td>
<td>

off



</td>
<td>

off



</td>
<td>

 



</td>
</tr>
<tr>
<td>

`space-infix-ops`



</td>
<td>

error



</td>
<td>

error



</td>
<td>

 



</td>
</tr>
<tr>
<td>

`space-return-throw-case`



</td>
<td>

error



</td>
<td>

error



</td>
<td>

 



</td>
</tr>
<tr>
<td>

`space-unary-ops`



</td>
<td>

off



</td>
<td>

**error**



</td>
<td>

 



</td>
</tr>
<tr>
<td>

`max-nested-callbacks`



</td>
<td>

off



</td>
<td>

**warning**



</td>
<td>

`3`



</td>
</tr>
<tr>
<td>

`one-var`



</td>
<td>

off



</td>
<td>

off



</td>
<td>

 



</td>
</tr>
<tr>
<td>

`wrap-regex`



</td>
<td>

off



</td>
<td>

off



</td>
<td>

 



</td>
</tr>
</table>

<a name="loio1ba0e44f1036439b95f25527664f14f7__table_ung_gjn_np"/>Legacy


<table>
<tr>
<th>

Rule



</th>
<th>

ESLint default



</th>
<th>

SAPUI5 Core



</th>
</tr>
<tr>
<td>

`max-depth`



</td>
<td>

off



</td>
<td>

off



</td>
</tr>
<tr>
<td>

`max-len`



</td>
<td>

off



</td>
<td>

off



</td>
</tr>
<tr>
<td>

`max-params`



</td>
<td>

off



</td>
<td>

off



</td>
</tr>
<tr>
<td>

`max-statements`



</td>
<td>

off



</td>
<td>

off



</td>
</tr>
<tr>
<td>

`no-bitwise`



</td>
<td>

off



</td>
<td>

off



</td>
</tr>
<tr>
<td>

`no-plus`



</td>
<td>

off



</td>
<td>

off



</td>
</tr>
</table>

For more information about the rules, see the rules documentation provided on [http://eslint.org](http://eslint.org).

