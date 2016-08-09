android 4.1, 4.2, 4.3 native browser is broken about css `position` dynamic handling.

# demo

Start server.

```
$ python -m SimpleHTTPServer
```

Access `index.html` with android 4.1, 4.2, 4.3 native browser. (not chrome)

When you scroll down, orange box is changed to `position:fixed`.
But yellow inner box is still moving up leaving from parent orange box.

# my estimation

This issue happens only with changing `position` by javascript.
Broken browser may fail to setup `fixed` state correctly.

If you put `fixed` in initial css,
yellow inner box disappears during `position:relative` conversely.

# files

`index.html`: main issue.

`crash.html`: browser crash case.

