# Changelog

## 0.2.0 (2018-07-20)
- Change `MARA_CONFIG` to `MARA_CONFIG_MODULE` to be consistent with former name
- Remove the flask config view (moved to the mara-app package).
- Add `needs_set=False` argument to the `@declare_config()` to show 
  that a config needs to be set by a `@set_config()` before it's usable. 
  A config item which is not set but used will `raise NotImplementedError()`.
  Also add this information to the ConfigDisplay so that it can be shown in 
  the UI.
* Add `mara config print`: printing the config (moved from mara-cli package).
  Needs a `mara-cli>=0.2` package, to get the short 'config' subcommand name, 
  otherwise the command is exposed as `mara mara_config.config print`.
* Add `mara config validate`: validates the config if all `needs_set=true` 
  config items are set.
* Add `mara config generate_local_setup`: generates rudimentary content for 
  `local_setup.py` for all unset but `needs_set=True` config items.

### Required changes:
* Change any `def MARA_CONFIG()` to `def MARA_CONFIG_MODULE()`.
* Adjust the dependecies for `mara-app` (to get the mara_config based `/configuration`
  page) and `mara-cli` (to get the short subcommands and remove the otherwise 
  duplicated `mara print_config` command).

## 0.1.4 (2018-07-09)
- Adjust sys.path so that the app repo is sys.path and the 
  MARA_APP can be imported. Unfortunately, you still need to do
  `init_mara_config_once()` before `import app.app`  (if you put 
  your mara app in the default package structure).

## 0.1.3 (2018-07-03)
- Add `init_mara_config_once()` for usage in one-off scripts

## 0.1.0 - 0.1.1 (2018-05-22)

- Initial version with this functionality:
  - config system based on functions and decorators
  - app composing by registering declared functionality in wanted packages
  - (optional) flask config view 
  - Support to replace functionality in other packages via monkey patching
- automatically upload tags to pypi

