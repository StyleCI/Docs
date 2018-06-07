# Configuration

StyleCI provides two ways to configure your repos. You can apply configuration either by committing a .styleci.yml file to the root of your repo, or by visiting the settings page for your repo, and applying it there.

Configuration is formatted as a series of keys and their values, like the following:

```yaml
key1:
  key2:
    - value1
    - value2
  key3:
    - value3
key4:
  - value4
```

As can be seen, key4 has a single value (value4) and key1 has two sub-keys (key2 and key3), each of which have their own values (value1/value2 and value3, respectively). A StyleCI configuration, written like above in either your .styleci.yml file or in the settings page, is therefore like a tree of options.

> {info} Setting configuration through the browser will override all config set in the .styleci.yml file.

> {danger} If you want to use our PHP header checking facility, you must configure that part on the settings page as that's the only part of the configuration not available through the .styleci.yml file.

<a name="choosing-languages"></a>
## Choosing Languages

If you are on a newer paid plan, then you will have access to support for fixing PHP, JS, CSS, Vue.js, Python, and more. If you are on the open source plan, then you will get support for PHP baked in.

The configuration format differs significantly between PHP and other languages. As well as this, the config file format used for multiple languages rather than just PHP will only be accepted if your plan supports it.

> {info} By default, we will assume you have a PHP repo, and so if you provide no config, you will get all the defaults.

<a name="fixing-strategies"></a>
## Fixing Strategies

Our PHP fixing works by applying fixers to files that fix specific things. By comparison, our new language support works differently by reprinting the entire file. It may seem like there's less being fixed because they are fewer options, but in fact, this is not the case. Everything is being standardized, and the configuration allows you to choose how you want things to look.

<a name="php-only-mode"></a>
## PHP Only Mode

In the absence of an open source plan, StyleCI will expect your configuration to be formatted in a PHP-only manner. Note that configuration written this way can later be embedded into a multiple-language format configuration if you change to a plan that accommodates this.

To demonstrate this, below is the contents of an example .styleci.yml file, using all PHP-only config features available:

```yaml
preset: recommended

risky: false

enabled:
  - long_array_syntax
  - strict
  - unalign_double_arrow

disabled:
  - align_double_arrow
  - short_array_syntax

finder:
  exclude:
    - "tests"
  name:
    - "*.php"
  not-name:
    - "*Stub.php"
  contains:
    - "Foo"
  not-contains:
    - "config"
  path:
    - "foo/Stuff"
  not-path:
    - "libraries"
  depth:
    - "< 3"
```

> {note} This is a contrived example, and is not recommended for usage in any actual projects.

Any key shown above that is not included will be replaced with its
[default value](default-configuration).

### Presets

We provide a few premade configurations that tend to be useful. After choosing a preset with the 'preset' key as above, you can add extra config that will override settings your preset contains. The 'recommended' preset is enabled by default.

Check out the [Presets](presets.md) page for more details.

### Risky

Some of our fixers do things that can change code behavior in weird cases. It's generally not an issue, but if you're concerned about an odd piece of code you've written clashing with these fixes, you can disable them by setting 'risky' to false. It'll be set to true by default.

If you're not sure whether something will break, feel free to check out all our risky PHP fixers [here](fixers.md), denoted by a warning of changing code behavior below their name.

### Enabled/Disabled

These two keys allow you to cherry-pick which fixers will and won't be used, by bullet-point listing them as in the example. Have a look [here](fixers.md) for details on each fixer.

> {danger} Some fixers are incompatible with each other - make sure not to enable any such two at once, or the fix will fail.

### Finder

Our fixers will look everywhere except for a few preset paths by default. However, you can fine-tune which places to fix and which to ignore with the 'finder' key. See more on how this works [here](finder.md).

<a name="multiple-languages"></a>
## Multiple Languages

For paid-plan users, our new configuration format provides top-level keys to specify separate options for each supported language. This allows you to fine-tune each language independently for a more comprehensive code fixing experience.

Each language's configuration must now fall under said language's name. For instance, observe the example config file below:

```yaml
php:
  preset: laravel
  risky: true
  enabled:
    - long_array_syntax
  disabled:
    - align_double_arrow
  finder:
    exclude:
      - modules
      - node_modules
      - storage
      - vendor
    name: "*.php"
    not-name: "*.blade.php"
js:
  tab-width: 4
  use-tabs: false
  print-width: 120
  double-quotes: false
  trailing-commas: es5
  semicolons: true
  arrow-parens: avoid
  bracket-spacing: true
  finder:
    exclude:
      - modules
      - node_modules
      - storage
      - vendor
    name:
      - "*.js"
      - "*.jsx"
    not-name:
      - "*.min.js"
ts: false
css: false
py: true
```

As can be seen, the 'php', 'js', 'ts', 'css' and 'py' keys each allow for PHP, Javascript, Typescript, CSS and Python configuration, respectively. Writing 'false' after such a key disables fixing for that language; writing 'true' enables our default fixes for it. If you want to customize, you can instead write out the configuration manually under the language you want.

In the above example, it can be seen that custom PHP and Javascript configurations are used, along with the default Python one and no other languages.

> {info} If you removed the 'ts' or 'css' keys, the behavior would remain the same; removing any such language's key replaces it with its default behavior, ie. 'true' for PHP and 'false' for all others.

You may notice that the PHP and Javascript configurations look different. In fact, every languge has its own separate configuration options, with PHP retaining the PHP-only ones.

We describe each new language's options below. For all languages, the [finder](finder.md) key works the same.

### Javascript Config

Setting 'js: true' translates to the following:

```yaml
js:
  tab-width: 4
  use-tabs: false
  print-width: 120
  double-quotes: false
  trailing-commas: es5
  semicolons: true
  arrow-parens: avoid
  bracket-spacing: true
  finder:
    exclude:
      - modules
      - node_modules
      - storage
      - vendor
    name:
      - "*.js"
      - "*.jsx"
    not-name:
      - "*.min.js"
```

* Valid values for tab-width are integers between 2 and 8. We'd recommend either 2 or 4.
* Valid values for use-tabs are false and true.
* Valid values for print-width are integers between 20 and 200. We'd recommend 80, 100, or 120.
* Valid values for double-quotes are false and true.
* Valid values for trailing-commas are none, es5, or all.
* Valid values for semicolons are false and true.
* Valid values for arrow-parens are avoid and always.
* Valid values for bracket-spacing are false and true.

### Typescript Config

Setting 'ts: true' translates to the following:

```yaml
ts:
  tab-width: 4
  use-tabs: false
  print-width: 120
  double-quotes: false
  trailing-commas: es5
  semicolons: true
  arrow-parens: avoid
  bracket-spacing: true
  finder:
    exclude:
      - modules
      - node_modules
      - storage
      - vendor
    name: "*.ts"
```

* Valid values for tab-width are integers between 2 and 8. We'd recommend either 2 or 4.
* Valid values for use-tabs are false and true.
* Valid values for print-width are integers between 20 and 200. We'd recommend 80, 100, or 120.
* Valid values for double-quotes are false and true.
* Valid values for trailing-commas are none, es5, or all.
* Valid values for semicolons are false and true.
* Valid values for arrow-parens are avoid and always.
* Valid values for bracket-spacing are false and true.

### CSS Config

Setting 'css: true' translates to the following:

```yaml
css:
  tab-width: 4
  use-tabs: false
  print-width: 120
  double-quotes: false
  finder:
    exclude:
      - modules
      - node_modules
      - storage
      - vendor
    name:
      - "*.css"
      - "*.scss"
      - "*.less"
```

* Valid values for tab-width are integers between 2 and 8. We'd recommend either 2 or 4.
* Valid values for use-tabs are false and true.
* Valid values for print-width are integers between 20 and 200. We'd recommend 80, 100, or 120.
* Valid values for double-quotes are false and true.

### Vue Config

Setting 'vue: true' translates to the following:

```yaml
vue:
  tab-width: 4
  use-tabs: false
  print-width: 120
  double-quotes: false
  trailing-commas: es5
  semicolons: true
  arrow-parens: avoid
  bracket-spacing: true
  finder:
    exclude:
      - modules
      - node_modules
      - storage
      - vendor
    name: "*.vue"
```

* Valid values for tab-width are integers between 2 and 8. We'd recommend either 2 or 4.
* Valid values for use-tabs are false and true.
* Valid values for print-width are integers between 20 and 200. We'd recommend 80, 100, or 120.
* Valid values for double-quotes are false and true.
* Valid values for trailing-commas are none, es5, or all.
* Valid values for semicolons are false and true.
* Valid values for arrow-parens are avoid and always.
* Valid values for bracket-spacing are false and true.

### Python Config

> {info} Support for Python is currently in beta; a host of features, such as configuring indentation, are under development and will become available as the beta progresses. Any feedback you have on these features is a big help.

Setting 'py: true' translates to the following:

```yaml
py:
  version: 3
  finder:
    exclude:
      - modules
      - node_modules
      - storage
      - vendor
    name: "*.py"
```

* The version key specifies the Python grammar version to use. 2 and 3 are allowed values, 3 being the default.

<a name="default-configuration"></a>
## Default Configuration

Our default (PHP-only) configuration is as follows:

```yaml
  preset: recommended
  risky: true
  finder:
    exclude:
      - modules
      - node_modules
      - storage
      - vendor
    name: "*.php"
    not-name: "*.blade.php"
```

This configuration, in multi-language mode, is equivalent to:

```yaml
php: true
js: false
ts: false
css: false
vue: false
py: false
```

> {info} We're in the process of migrating our documenation. You can find the original docs [here](https://styleci.readme.io/docs/multi-lang).
