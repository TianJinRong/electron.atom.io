---
version: v0.28.0
category: API
title: 'Global Shortcut'
source_url: 'https://github.com/atom/electron/blob/master/docs/api/global-shortcut.md'
---

# global-shortcut

The `global-shortcut` module can register/unregister a global keyboard shortcut
in operating system, so that you can customize the operations for various shortcuts.
Note that the shortcut is global, even if the app does not get focused, it will still work.

```javascript
var globalShortcut = require('global-shortcut');

// Register a 'ctrl+x' shortcut listener.
var ret = globalShortcut.register('ctrl+x', function() { console.log('ctrl+x is pressed'); })

if (!ret) {
  console.log('registration failed');
}

// Check whether a shortcut is registered.
console.log(globalShortcut.isRegistered('ctrl+x'));

// Unregister a shortcut.
globalShortcut.unregister('ctrl+x');

// Unregister all shortcuts.
globalShortcut.unregisterAll();
```

## globalShortcut.register(accelerator, callback)

* `accelerator` [Accelerator](http://electron.atom.io/docs/v0.28.0/api/accelerator)
* `callback` Function

Registers a global shortcut of `accelerator`, the `callback` would be called when
the registered shortcut is pressed by user.

## globalShortcut.isRegistered(accelerator)

* `accelerator` [Accelerator](http://electron.atom.io/docs/v0.28.0/api/accelerator)

Returns `true` or `false` depending on if the shortcut `accelerator` is registered.

## globalShortcut.unregister(accelerator)

* `accelerator` [Accelerator](http://electron.atom.io/docs/v0.28.0/api/accelerator)

Unregisters the global shortcut of `keycode`.

## globalShortcut.unregisterAll()

Unregisters all the global shortcuts.
