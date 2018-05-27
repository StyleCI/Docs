# Configuration

StyleCI provides two ways to configure your repos. You can apply configuration either by committing a .styleci.yml file to the root of your repo, or by visiting the settings page for your repo, and applying it there.

> {info} Setting configuration through the browser will override all config set in the .styleci.yml file.

## Fixing Strategies

Our PHP fixing works by applying fixers to files that fix specific things. By comparison, our new language support works differently by reprinting the entire file. It may seem like there's less being fixed because they are fewer options, but in fact, this is not the case. Everything is being standardized, and the configuration allows you to choose how you want things to look.

## Choosing Languages

If you are on a newer paid plan, then you will have access to support for fixing PHP, JS, CSS, Vue.js, Python, and more. If you are on the open source plan, then you will get support for PHP baked in.

The format of configuration files when configuring multiple languages is different, and the multiple lanauges format of config file is only valid for plans that support it.

> {info} By default, we will assume you have a PHP repo, and so if you provide no config, you will get all the defaults.

## PHP Only Mode

Our default configuration is as follows:

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

> {danger} If you want to use our PHP header checking facility, you must configure that part on the settings page as that's the only part of the configuration not available through the .styleci.yml file.

## Multiple Languages

In order to accommodate multiple languages, we are adding top-level config to configure each language.

Our default configuration is equivalent to:

```yaml
php: true
js: false
ts: false
css: false
vue: false
py: false
```

You can enable the languages you want by either setting the value for each to true, to a configuration map.

### PHP

TODO.

### JS/TS

TODO.

### CSS/SCSS/Less

TODO.

### Vue.js

TODO.

### Python

TODO.
