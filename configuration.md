# Configuration

StyleCI provides two ways to configure your repos. You can apply configuration either by committing a `.styleci.yml` file to the root of your repo, or by visiting the settings page for your repo, and applying it there.

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

As can be seen, key4 has a single value (value4) and key1 has two sub-keys (key2 and key3), each of which have their own values (value1/value2 and value3, respectively). A StyleCI configuration, written like above in either your `.styleci.yml` file or in the settings page, is therefore like a tree of options.

> {info} Setting configuration through the browser will override all config set in the `.styleci.yml` file.

> {danger} If you want to use our PHP header checking facility, you must configure that part on the settings page as that's the only part of the configuration not available through the `.styleci.yml` file.

<a name="choosing-languages"></a>
## Choosing Languages

If you are on a newer paid plan, then you will have access to support for fixing PHP, JS, CSS, Vue.js, Python, and more. If you are on the open source plan, then you will get support for PHP baked in.

The configuration format differs significantly between PHP and other languages. As well as this, the format used for multiple languages rather than just PHP will only be accepted if your plan supports it.

> {info} By default, we will assume you have a PHP repo, and so if you provide no config, you will get all the defaults.

<a name="fixing-strategies"></a>
## Fixing Strategies

Our PHP fixing works by applying fixers to files that fix specific things. By comparison, our new language support works differently by reprinting the entire file. It may seem like there's less being fixed because they are fewer options, but in fact, this is not the case. Everything is being standardized, and the configuration allows you to choose how you want things to look.

<a name="php-only-mode"></a>
## PHP-Only Mode

If you happen to be using an open-source plan, you will have access to PHP-only features. These are detailed [here](standalone-php).

<a name="all-languages-mode"></a>
## All-Languages Mode

If you have a paid plan, you'll have access to configuration features for every language StyleCI supports. Find out more about these options [here](all-languages).

<a name="default-configuration"></a>
## Default Configuration

Our default (PHP-only) configuration, used to define any undefined keys in your configuration, is as follows:

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

You can read more about each option [here](standalone-php); in essence, the default mode uses recommended fixers and ignores paths and file suffixes that are usually undesirable to fix.

This configuration, in all-languages mode, is equivalent to:

```yaml
php: true
js: false
ts: false
css: false
vue: false
py: false
```

You can read more about each option [here](all-languages). It simply disables all languages other than PHP, using its default settings above.
