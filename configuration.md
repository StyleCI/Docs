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
