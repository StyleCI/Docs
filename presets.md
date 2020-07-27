# PHP Presets

We have 6 non-empty presets to choose from to make your code look totally gorgeous. Our [`recommended`](#recommended) preset is enabled by default on all repos. We also have an additional preset, `none`, which enables no fixers.

By default, "risky" heuristic fixers are disabled. When risky mode is enabled, all risky and non-risky fixers provided by a preset will be enabled, and when risky mode is disabled, only the non-risky fixers will be enabled. For example, when enabling the [`psr12`](#psr12) preset, with `risky: false` ot without specifying the `risky` mode, the [`no_trailing_whitespace_in_string`](/fixers#no_trailing_whitespace_in_string), [`no_unreachable_default_argument_value`](/fixers#no_unreachable_default_argument_value), and [`psr4`](/fixers#psr4) fixers will not be enabled by the preset.

__STYLECI_PRESET_DOCS__
