# PHP-Only Mode

In the absence of a paid plan, StyleCI will expect your configuration to be formatted in a PHP-only manner. Note that configuration written this way can later be embedded into a multiple-language format if you change to a plan that accommodates this.

To demonstrate this, below is the contents of an example `.styleci.yml` file, using all PHP-only config features available:

```yaml
risky: false

version: 8.1

preset: recommended

tab-width: 4

use-tabs: false

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

> {danger} DO NOT COPY THIS CONFIG FILE TO YOUR PROJECT AS IS! It only exists to show off all the configuration options we have.

Any key shown above that is not included will be replaced with its [default value](configuration#default-configuration).

<a name="risky"></a>
## Risky

Some of our fixers do things that can change code behavior, by design. Risky mode is disabled by default, but you can enable the use of such fixers by `risky` to true. All of our safe and risky fixers are documented [here](fixers).

<a name="version"></a>
## Version

It is possible to set the PHP version your code will be parsed using using the `version` option. `7.4`, `8.0`, and `8.1` are the allowed values, and additionally, `7` is an alias for `7.4` and `8` is an alias for `8.1`. PHP version 8.1 is the default version.

<a name="presets"></a>
## Presets

We provide a few premade configurations that tend to be useful. After choosing a preset with the `preset` key as above, you can add extra config that will override settings your preset contains. The `recommended` preset is enabled by default.

Check out the [Presets](presets) page for more details.

<a name="indentation"></a>
## Indentation

It is possible to configure the desired indentation style by setting the `tab-width` value to either `2` or `4` (defaults to `4`) and the `use-tabs` value to either `true` or `false` (defaults to `false`). If you have enabled the `indentation` fixer, then all your indentation will be updated to match this style (this fixer is enabled by default). If you do not enable this fixer, these config options will only affect generated or directly fixed code.

<a name="enabled-disabled"></a>
## Enabled/Disabled

These two keys allow you to cherry-pick which fixers will and won't be used, by bullet-point listing them as in the example. Have a look [here](fixers) for details on each fixer.

> {danger} Some fixers are incompatible with each other - make sure not to enable any such two at once, or the fix will fail.

<a name="finder"></a>
## Finder

Our fixers will look everywhere except for a few preset paths by default. However, you can fine-tune which places to fix and which to ignore with the `finder` key. See more on how this works [here](finder).
