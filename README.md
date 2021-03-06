# nw-appmenu

Helper to work with application menu in nwjs (node-webkit)

#### Install:

```
npm install nw-appmenu
```

#### Example:

```js
var AppMenu = require('nw-appmenu');

// we will add Zoom In, Zoom Out, Inspector, Reload, Help items to window menu
var menu = {
  'Window': {
    'separator': 'separator',
    'Zoom in': {
      click: function () {
        gui.Window.get().zoomLevel += 0.5;
      },
      key: '+'
    },
    'Zoom out': {
      click: function () {
        gui.Window.get().zoomLevel -= 0.5;
      },
      key: '-'
    },
    'Zoom to noraml': {
      click: function () {
        gui.Window.get().zoomLevel = 0;
      },
      key: '0'
    },
    'separator2': 'separator',
    Inspector: {
      click: function () {
        var win = gui.Window.get();
        if (win.isDevToolsOpen()) {
          win.closeDevTools();
        } else {
          win.showDevTools();
        }
      },
      key: 'i'
    },
    Reload: {
      click: function () {
        gui.Window.get().reloadDev();
      },
      key: 'r'
    },
    Help: function() {
      window.alert("help window");
    }
  }
};

AppMenu.createAndExtend(menu);

```

![screen shot 2015-04-29 at 1 55 56](https://cloud.githubusercontent.com/assets/26019/7377889/6eb537e4-ee13-11e4-9127-d687afa0e968.png)

I extrac this code from [Postbird](https://github.com/Paxa/postbird), please see `example_app` folder for more features and options.