# Configuration

StyleCI provides two ways to configure your repos. Choose the one that suits you best.

<a name="file-based"></a>
## File Based

You can apply configuration by commiting a `.styleci.yml` file to your project's root. The configuration file uses the [YAML format](https://yaml.org/spec/1.2/spec.html#Preview).

<!-- -->
> {danger} If you want to use our PHP header checking facility, you must configure that part on the settings page; it's the only part of the configuration not available through the `.styleci.yml` file.

<a name="browser-based"></a>
## Browser Based

You can configure the settings for a repository by opening your dashboard and clicking the gear icon right next to your repository.

> {warn} Setting configuration through the browser will override all config set in the `.styleci.yml` file.

<a name="choosing-languages"></a>
## Choosing Languages

If you're on a newer paid plan, then you'll have access to support for fixing PHP, JS, CSS, Vue.js, Python, and more. If you're on the open source plan, then you'll get support for standalone PHP.

The configuration format differs significantly between PHP and other languages. Also, the format used for multiple languages rather than just PHP will only be accepted if your plan supports it.

> {info} By default, we will assume you have a PHP repo, and so if you provide no config, you will get all the defaults.

<a name="php-only-mode"></a>
### PHP-Only Mode

If you happen to be using an open-source plan, you will have access to PHP-only features. These are detailed [here](standalone-php).

<a name="multi-languages-mode"></a>
### Multi-Language Mode

If you have a paid plan, you'll have access to configuration features for every language StyleCI supports. Find out more about these options [here](multi-language).

<a name="default-configuration"></a>
## Default Configuration

Our default (PHP-only) configuration looks like this:

```yaml
risky: false
version: 8.3
preset: recommended
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
```

You only need to define the configuration options you want to override, any other options are merged with the default.

You can read more about each option [here](standalone-php); in essence, the default mode uses recommended fixers and ignores paths and file suffixes that are usually undesirable to fix.

This configuration, in multi-language mode, is equivalent to:

```yaml
php: true
js: false
ts: false
css: false
vue: false
py: false
```

You can read more about each option [here](multi-language). It simply disables all languages other than PHP, using its default settings above.
