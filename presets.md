# PHP Presets

We have 5 presets to choose from to make your code look totally gorgeous. Our [`recommended`](#recommended) preset is enabled by default on all repos. We also have an additional preset, `none`, which enables no fixers.

Note that if you have disabled the "risky" heuristic fixers, then any and all such fixers will already excluded when selecting a preset. For example, when enabling the [`laravel`](#laravel) preset, with `risky: false`, the [`psr4`](/fixers#psr4), [`no_alias_functions`](/fixers#no_alias_functions), and [`simplified_null_return`](/fixers#simplified_null_return) fixers will not be enabled by the preset.

__STYLECI_PRESET_DOCS__
