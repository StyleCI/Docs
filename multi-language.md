# Multi-Language Mode

For paid-plan users, our new configuration format provides top-level keys to specify separate options for each supported language. This allows you to fine-tune each language independently for a more comprehensive code fixing experience.

The configuration for each language must now fall under the relevant name. For instance, observe the example config file below:

```yaml
php:
  risky: true
  version: 8.3
  preset: laravel
  enabled:
    - ternary_to_elvis_operator
  disabled:
    - single_import_per_statement
  monolithic: true
  finder:
    exclude:
      - "modules"
      - "node_modules"
      - "nova"
      - "nova-components"
      - "storage"
      - "spark"
      - "vendor"
    name: "*.php"
    not-name:
      - "*.blade.php"
      - "_ide_helper.php"
js:
  tab-width: 4
  use-tabs: false
  print-width: 120
  double-quotes: false
  trailing-commas: es5
  semicolons: true
  arrow-parens: always
  bracket-same-line: false
  bracket-spacing: true
  finder:
    exclude:
      - "modules"
      - "node_modules"
      - "nova"
      - "nova-components"
      - "storage"
      - "spark"
      - "vendor"
    name:
      - "*.js"
      - "*.jsx"
    not-name:
      - "*.min.js"
ts: false
css: false
py: true
```

As can be seen, the `php`, `js`, `ts`, `css` and `py` keys each allow for PHP, Javascript, Typescript, CSS and Python configuration respectively. Writing `false` after such a key disables fixing for that language; writing `true` enables our default fixes for it. If you want to customize, you can instead write out the configuration manually under the language you want.

In the above example, it can be seen that custom PHP and Javascript configurations are used, along with the default Python one and no other languages.

> {info} If you removed the `ts` or `css` keys, the behavior would remain the same; removing any such language's key replaces it with its default behavior, ie. `true` for PHP and `false` for all others.

You may notice that the PHP and Javascript configurations look different. In fact, every language has its own separate configuration options, with PHP retaining the PHP-only ones.

We describe each new language's options below. For all languages, the [finder](finder) key works the same.

<a name="php-config"></a>
## PHP Config

Setting `php: true` translates to the following:

```yaml
php:
  risky: false
  version: 8.3
  preset: recommended
  monolithic: true
  tab-width: 4
  use-tabs: false
  finder:
    exclude:
      - "modules"
      - "node_modules"
      - "nova"
      - "nova-components"
      - "storage"
      - "spark"
      - "vendor"
    name: "*.php"
    not-name:
      - "*.blade.php"
      - "_ide_helper.php"
```

PHP configuration is the same as before, other than that all PHP config options must fall under the `php` key as above. Read more about PHP configuration [here](standalone-php).

<a name="javascript-config"></a>
## Javascript Config

Setting `js: true` translates to the following:

```yaml
js:
  tab-width: 4
  use-tabs: false
  print-width: 120
  double-quotes: false
  trailing-commas: es5
  semicolons: true
  arrow-parens: always
  bracket-same-line: false
  bracket-spacing: true
  finder:
    exclude:
      - "modules"
      - "node_modules"
      - "nova"
      - "nova-components"
      - "storage"
      - "spark"
      - "vendor"
    name:
      - "*.js"
      - "*.jsx"
    not-name:
      - "*.min.js"
```

* Valid values for `tab-width` are `2` and `4`.
* Valid values for `use-tabs` are `false` and `true`.
* Valid values for `print-width` are integers between `20` and `200`. We'd recommend `80`, `100`, or `120`.
* Valid values for `double-quotes` are `false` and `true`.
* Valid values for `trailing-commas` are `none`, `es5`, or `all`.
* Valid values for `semicolons` are `false` and `true`.
* Valid values for `arrow-parens` are `avoid` and `always`.
* Valid values for `bracket-same-line` are `false` and `true`.
* Valid values for `bracket-spacing` are `false` and `true`.

<a name="typescript-config"></a>
## Typescript Config

Setting `ts: true` translates to the following:

```yaml
ts:
  tab-width: 4
  use-tabs: false
  print-width: 120
  double-quotes: false
  trailing-commas: es5
  semicolons: true
  arrow-parens: always
  bracket-same-line: false
  bracket-spacing: true
  finder:
    exclude:
      - "modules"
      - "node_modules"
      - "nova"
      - "nova-components"
      - "storage"
      - "spark"
      - "vendor"
    name: "*.ts"
```

* Valid values for `tab-width` are `2` and `4`.
* Valid values for `use-tabs` are `false` and `true`.
* Valid values for `print-width` are integers between `20` and `200`. We'd recommend `80`, `100`, or `120`.
* Valid values for `double-quotes` are `false` and `true`.
* Valid values for `trailing-commas` are `none`, `es5`, or `all`.
* Valid values for `semicolons` are `false` and `true`.
* Valid values for `arrow-parens` are `avoid` and `always`.
* Valid values for `bracket-same-line` are `false` and `true`.
* Valid values for `bracket-spacing` are `false` and `true`.

<a name="css-config"></a>
## CSS Config

Setting `css: true` translates to the following:

```yaml
css:
  tab-width: 4
  use-tabs: false
  print-width: 120
  double-quotes: false
  finder:
    exclude:
      - "modules"
      - "node_modules"
      - "nova"
      - "nova-components"
      - "storage"
      - "spark"
      - "vendor"
    name:
      - "*.css"
      - "*.scss"
      - "*.less"
```

* Valid values for `tab-width` are `2` and `4`.
* Valid values for `use-tabs` are `false` and `true`.
* Valid values for `print-width` are integers between `20` and `200`. We'd recommend `80`, `100`, or `120`.
* Valid values for `double-quotes` are `false` and `true`.

<a name="vue-config"></a>
## Vue.js Config

Setting `vue: true` translates to the following:

```yaml
vue:
  tab-width: 4
  use-tabs: false
  print-width: 120
  double-quotes: false
  trailing-commas: es5
  semicolons: true
  arrow-parens: always
  bracket-same-line: false
  bracket-spacing: true
  indent-script-and-style: false
  whitespace-sensitivity: css
  finder:
    exclude:
      - "modules"
      - "node_modules"
      - "nova"
      - "nova-components"
      - "storage"
      - "spark"
      - "vendor"
    name: "*.vue"
```

* Valid values for `tab-width` are `2` and `4`.
* Valid values for `use-tabs` are `false` and `true`.
* Valid values for `print-width` are integers between `20` and `200`. We'd recommend `80`, `100`, or `120`.
* Valid values for `double-quotes` are `false` and `true`.
* Valid values for `trailing-commas` are `none`, `es5`, or `all`.
* Valid values for `semicolons` are `false` and `true`.
* Valid values for `arrow-parens` are `avoid` and `always`.
* Valid values for `bracket-same-line` are `false` and `true`.
* Valid values for `bracket-spacing` are `false` and `true`.
* Valid values for `indent-script-and-style` are `false` and `true`.
* Valid values for `whitespace-sensitivity` are `css`, `strict` and `ignore`.

<a name="python-config"></a>
## Python Config

Setting `py: true` translates to the following:

```yaml
py:
  version: 3.11
  preset: pep8
  options:
    tab-width: 4
    use-tabs: false
    print-width: 120
    multiline-split-indent: 4
    join-short-lines: false
    comment-indent: 4
  finder:
    exclude:
      - "modules"
      - "node_modules"
      - "nova"
      - "nova-components"
      - "storage"
      - "spark"
      - "vendor"
    name: "*.py"
```

* The `version` key specifies the Python grammar version to use. `2.7` and `3.11` are allowed values, `3.11` being the default, and additionally, `2` is an alias for `2.7` and `3` is an alias for `3.11`.
* Valid values for the `preset` key are `pep8`, `google`, `chromium` or `facebook`. We'd recommend either `pep8` or `google`.
* The `options` key contains several suboptions for further, fine-tuned customizations. These options are as follows:
    * Valid values for `tab-width` are `2` and `4`.
    * Valid values for `use-tabs` are `false` and `true`.
    * Valid values for `print-width` are integers between `20` and `200`. We'd recommend `80`, `100`, or `120`.
    * The `multiline-split-indent` key specifies the extra indentation used when a line is split across several lines. Valid values are integers between `2` and `8`. We'd recommend `4`.
    * The `join-short-lines` key specifies whether to join several short lines into one, eg. making a small 'if' statement a one-liner. Valid values are `false` or `true`.
    * The `comment-indent` specifies indentation required after a line for a trailing comment. Valid values are integers between `2` and `8`.

Note that for Python, we allow a preset along with a set of extra options for fine-tuning their behavior. The presets will have the side effect of changing the defaults for `options`, which are overriden by setting these keys explicitly:

* `pep8` will set `use-tabs` to `false`, `print-width` to `79`, `tab-width` to `4`, `multiline-split-indent` to `4`, `join-short-lines` to `true` and `comment-indent` to 2.
* `google`, `facebook` and `chromium` will all do the same, albeit setting `column-width` to `80`.

> {info} It's important to remember the preset does a lot more than just choose defaults for the `options` key - the internal differences in behavior will be noticeable and substantial, albeit not directly configurable. Hence, for example, choosing the `google` preset will add several subtle fixes configured to coding to this standard that would not be available otherwise.
