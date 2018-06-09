# PHP-Only Mode

In the absence of a paid plan, StyleCI will expect your configuration to be formatted in a PHP-only manner. Note that configuration written this way can later be embedded into a multiple-language format if you change to a plan that accommodates this.

To demonstrate this, below is the contents of an example `.styleci.yml` file, using all PHP-only config features available:

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

Any key shown above that is not included will be replaced with its [default value](configuration#default-configuration).

<a name="presets"></a>
## Presets

We provide a few premade configurations that tend to be useful. After choosing a preset with the `preset` key as above, you can add extra config that will override settings your preset contains. The `recommended` preset is enabled by default.

Check out the [Presets](presets) page for more details.

<a name="risky"></a>
## Risky

Some of our fixers do things that can change code behavior in weird cases. It's generally not an issue, but if you're concerned about an odd piece of code you've written clashing with these fixes, you can disable them by setting `risky` to false. It'll be set to true by default.

If you're not sure whether something will break, feel free to check out all our risky PHP fixers [here](fixers), denoted by a warning of changing code behavior below their name.

<a name="enabled-disabled"></a>
## Enabled/Disabled

These two keys allow you to cherry-pick which fixers will and won't be used, by bullet-point listing them as in the example. Have a look [here](fixers) for details on each fixer.

> {danger} Some fixers are incompatible with each other - make sure not to enable any such two at once, or the fix will fail.

<a name="finder"></a>
## Finder

Our fixers will look everywhere except for a few preset paths by default. However, you can fine-tune which places to fix and which to ignore with the `finder` key. See more on how this works [here](finder).
