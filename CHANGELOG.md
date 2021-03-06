# Changelog

## 0.6.0 (2018-04-13)

### New features

* An array of functions can now be as the value of `converter` property,
  so that multi-argumnet options can use different conversion rules
  for different arguments (#14).
* Mutexes can now include positional arguments (#11).
* Added `hidden` property for arguments, options and commands,
  removing them from the autogenerated usage and help strings.
* Added `:group(name, ...)` method to Parser and Command objects, allowing
  custom grouping of arguments, options, and commands in autogenerated
  help string.
* Added `help_vertical_space` property for configuring number of extra
  newlines between help strings for different arguments and options in
  autogenerated help string.
* Added `usage_margin` and `usage_max_width` properties for configuring
  usage string autogeneration.
* Added `help_usage_margin` and `help_description_margin` properties
  for configuring help string autogeneration.
* Added `help_max_width` property. If set, descriptions in help string
  are automatically wrapped to fit into given number of columns.
* Argparse version is now available as `argparse.version`.

### Improvements

* `--` can now be used as a normal option name, with arguments
  after `--` always passed to it verbatim (#17).
* When generating help messages for options with arguments and multiple
  aliases, usage strings for different aliases are put on separate lines and
  vertically aligned (#15).

## 0.5.0 (2015-12-09)

### New features

* Actions can now be used to implement custom processing logic.
* Added actions for arguments.
* Added string aliases for actions such as `store_false`.
* Command actions are now called after the parsing, with result target
  as the argument.
* Added `command_target` property for storing name of used command.

### Improvements

* Improved error messages on missing arguments.
* `-f123` is now interpreted as `-f 123` when `-f` takes an optional argument.

## 0.4.1 (2015-08-08)

### Miscellaneous

* Added license header to `argparse.lua` for ease of bundling
  and packaging (#3).

## 0.4.0 (2015-06-20)

### Breaking changes

* Removed `aliases` property, aliases can now be set using several space
  separated strings as name, or, as it was possible before, by setting `name`
  property several times.

### New features

* Added `handle_options` property (#2).
* Often used properties now can be passed as arguments when calling or
  constructing an element.

### Improvements

* Cleaned up trailing whitespace in generated messages.

## 0.3.2 (2015-01-15)

### Miscellaneous

* Argparse no longer bundles 30log.

## 0.3.1 (2014-11-06)

### Fixes

* Fixed incompatibility with old Luarocks versions.

## 0.3.0 (2014-08-25)

### New features

* New `show_default` field disables automatic indication of default values in
  help messages.

### Improvements

* In default targets `-` is now replaced with `_`.
* Changed usage message generation to show options taking variable number of
  arguments after positional arguments.

### Fixes

* Fixed incompatibility with strict.lua and other checkers (#1).

## 0.2.0 (2014-03-09)

### New features

* Added mutually exclusive groups.
* Options and arguments can now be configured to use different argument
  placeholders for first, second, etc. arguments. E.g. `--pair <key> <value>`.

### Fixes

* Fixed script name inference not working for `Parser:get_help()` and
  `Parser:get_usage()` methods.

## 0.1.0 (2014-03-02)

Initial release.
