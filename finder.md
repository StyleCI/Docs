# Finder Configuration

The Finder configuration feature lets you nitpick exactly which files will and won't be fixed by StyleCI. By default, StyleCI will try and fix everything except for a few preset places (see the default configuration [here](configuration) to see which ones); our Finder options are the go-to fix for changing that behavior.

Take a look at the below example of a PHP-only configuration:

```yaml
risky: false

version: 8.1

presets: recommended

finder:
  exclude:
    - "tests"
    - "docs"
    - "log"
  name: "*.php"
  not-name:
    - "*Stub.php"
    - "*.blade.php"
  contains:
    - "Foo"
  not-contains:
    - "config"
  path:
    - "foo/Stuff"
  not-path:
    - "libraries"
  depth:
    - "< 2"
```

> {info} As in the above example, quotation marks around strings aren't necessary unless you're writing a regular expression.

Each option is followed by an arbitrarily long bullet-point list of strings to match with; if the list is one element long, it can be contracted, as with the `name` option above. Some options allow regular expressions.

We go through each of these options below.

<a name="exclude"></a>
## Exclude

Use the `exclude` option to exclude files in a given directory at the root of the project. In the above example, any path in the "tests", "docs" or "log" directories at the project root will be ignored.

<a name="name"></a>
## Name

Use `name` to identify the only file names to be analyzed. This is akin to a whitelist of file names to be checked. In the example, only "\*.php" file names will be fixed.

> {info} Regular expressions may be used with this option.

<a name="not-name"></a>
## Not-Name

Use `not-name` to identify file names to not be analyzed. It acts as the reverse of `name`, blacklisting files. In the example, "\*Stub.php" and "\*.blade.php" files will be ignored.

If a file matches both `name` and `not-name`, it will be ignored.

> {info} Regular expressions may be used with this option.

<a name="contains"></a>
## Contains

Use `contains` to only fix files whose contents contain certain strings or regexes. In the example, only files containing the string "Foo" will be fixed.

> {info} Regular expressions may be used with this option.

<a name="not-contains"></a>
## Not-Contains

Use `not-contains` to ignore files whose contents contain certain strings or regexes. In the example, files containing the string "config" will be ignored.

If a file matches both `contains` and `not-contains`, it will be ignored.

> {info} Regular expressions may be used with this option.

<a name="path"></a>
## Path

Use `path` to only fix files whose path matches any one element of a list of strings or regexes. In the example, only files with a path containing "foo/Stuff" will be fixed. The path this is checked against will be relative to the project root.

> {info} Regular expressions may be used with this option.

<a name="not-path"></a>
## Not-Path

Use `not-path` to ignore files whose path contains any element of a list of strings or regexes. In the example, files with a path containing "libraries" will be ignored.

If a file path matches both `path` and `not-path`, it will be ignored.

> {info} Regular expressions may be used with this option.

<a name="depth"></a>
## Depth

Use `depth` to identify how long a file's path should be, relative to the project root, to be fixed.

Each element of the list of strings has some possible formats, where N is a non-negative number:

* `"< N"`: Only fix files with path depth less than N.
* `"<= N"`: Only fix files with path depth less than or equal to N.
* `"== N"`: Only fix files with path depth equal to N.
* `"!= N"`: Only fix files with path depth not equal to N.
* `">= N"`: Only fix files with path depth greater than or equal to N.
* `"> N"`: Only fix files with path depth greater than N.
* `"N"` : Only fix files with path depth equal to N. This is
  equivalent to saying `"== N"` explicitly.

Listing multiple depths means all of them must be true. For instance, if you listed `"<= 3"`, `"!= 2"` and `"> 0"`, only paths of depth 3 or 1 would be considered.

In the above example, only files with path depth less than 2 relative to the project root are analyzed.
