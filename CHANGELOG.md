# Changelog

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

