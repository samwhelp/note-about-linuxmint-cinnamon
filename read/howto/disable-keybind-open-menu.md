---
title: 停用按鍵綁定「Super_L」開啟「Menu」
nav_order: 7022
has_children: false
parent: 如何
---


# 停用按鍵綁定「Super_L」開啟「Menu」




## 設定方式

按鍵綁定「Super_L」開啟「Menu」的設定，

儲存在「`~/.cinnamon/configs/menu@cinnamon.org/0.json`」

其中有一段「設定片段」如下

``` json
    "overlay-key": {
        "type": "keybinding",
        "description": "Keyboard shortcut to open and close the menu",
        "default": "Super_L::Super_R",
        "value": "<Alt>F1::"
    },
```

預設值是「`Super_L`」和「`Super_R`」。

設定值我設定為「`<Alt>F1`」，

也就是我改成按下「`Alt + F1`」才會開啟「主要功能選單」。




## 相關議題

| 相關議題 |
| ------- |
| [設定 Mouse Button Modifier](https://samwhelp.github.io/note-about-cinnamon/read/howto/config-mouse-button-modifier.html) |
