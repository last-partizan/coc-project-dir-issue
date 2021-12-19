# Reproduction steps

1. Open `src/app/assets/test.js`
2. `:edit src/app/core/test.py`

# Expected result

Using root `pyrightconfig.json`, this should be `info`.
```
  info: Cannot access member "missing_method" for type "Foo"
```

# Actual result:

```
  error: Cannot access member "missing_method" for type "Foo"
```

It probably uses src/app as root for finding config file.

`CocCommand workspace.workspaceFolders` returns this:
```
/tmp/test-project-dir/src/app
/tmp/test-project-dir
```
