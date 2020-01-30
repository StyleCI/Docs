# PHP Fixers

Our PHP fixing works by applying single-purposed transformations to files that fix specific issues.

Depending upon the [preset](presets), a default set of fixers will be included.
If you want more granular control, you can enable or disable specific fixers by adding them to your configuration:

```yaml
preset: recommended
enabled:
  - no_superfluous_phpdoc_tags
  - declare_strict_types
disabled:
  - align_double_arrow
  - include
```

> {danger} If you want to use our PHP header checking facility, you must configure that part on the settings page; it's the only part of the configuration not available through the `.styleci.yml` file.

__STYLECI_FIXER_DOCS__

---

Please note that much of the content on this page is Copyright (c) 2012-2018 Fabien Potencier and Dariusz Rumiński, licensed under [The MIT License](https://github.com/FriendsOfPHP/PHP-CS-Fixer/blob/master/LICENSE).
