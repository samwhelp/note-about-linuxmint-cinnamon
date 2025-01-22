---
title: 停用按鍵綁定「Super_L」開啟「Menu」
nav_order: 7022
has_children: false
parent: 如何
---


# 停用按鍵綁定「Super_L」開啟「Menu」


## 主題

* [設定檔路徑](#設定檔路徑)
* [設定方式](#設定方式)
* [相關議題](#相關議題)
* [衝突綁定](#衝突綁定)




## 設定檔路徑

舊版的設定檔路徑，放在「`~/.cinnamon/configs/menu@cinnamon.org/0.json`」

新版的設定檔路徑，改到「`~/.config/cinnamon/spices/menu@cinnamon.org/0.json`」

撰寫此文，採用的版本

``` sh
cinnamon --version
```

顯示

```
Cinnamon 6.4.6
```




## 設定方式


### 圖形介面操作

除了可以在「下方 Panel」的「Menu Icon」按下「滑鼠右鍵」出現一個「選單」，選擇「Configure」。

就會出現「Menu 設定對話框」。

可以找到「`Behvior / Keyboard shortcut to open and close the menu`」，

預設是綁定「`Super_L`」和「`Super_R`」。

可以按下「該按鈕」後，假設要改成「`<Alt>F1`」，就直接按下「`<Alt>F1`」。

若要「清除綁定」，則是按下「該按鈕」後，按下「`Backspace`」，就會變成「`unassigned`」。


### 修改設定檔

按鍵綁定「`Super_L`」開啟「Menu」的設定，

儲存在「「`~/.config/cinnamon/spices/menu@cinnamon.org/0.json`」這個檔案。

其中有一段「設定片段」類似如下

``` json
    "overlay-key": {
        "type": "keybinding",
        "description": "Keyboard shortcut to open and close the menu",
        "default": "Super_L::Super_R",
        "value": "<Alt>F1::"
    },
```

其中「預設值」是「`Super_L`」和「`Super_R`」。

至於「設定值」我設定為「`<Alt>F1`」，

也就是我改成按下「`Alt + F1`」才會開啟「主要功能選單」。


> 若是要「清除綁定」，「設定片段」則是改成如下

``` json
    "overlay-key": {
        "type": "keybinding",
        "description": "Keyboard shortcut to open and close the menu",
        "default": "Super_L::Super_R",
        "value": "::"
    },
```




## 相關議題

| 相關議題 |
| ------- |
| [設定「Mouse Button Modifier」](https://samwhelp.github.io/note-about-linuxmint-cinnamon/read/howto/config-mouse-button-modifier.html) |




## 衝突綁定

> 上面提到我設定「`Alt + F1`」才會開啟「主要功能選單」。

> 在「Cinnamon Desktop」，預設「`Alt + F1`」會觸發「`switch-to-workspace-up`」。

可以執行下面指令，找到該設定。

``` sh
gsettings list-recursively | grep '<Alt>F1'
```

顯示

```
org.cinnamon.desktop.keybindings.wm switch-to-workspace-up ['<Control><Alt>Up', '<Alt>F1']
org.cinnamon.desktop.keybindings.wm toggle-maximized ['<Alt>F10']
org.cinnamon.muffin.wayland.keybindings switch-to-session-1 ['<Primary><Alt>F1']
org.cinnamon.muffin.wayland.keybindings switch-to-session-10 ['<Primary><Alt>F10']
org.cinnamon.muffin.wayland.keybindings switch-to-session-11 ['<Primary><Alt>F11']
org.cinnamon.muffin.wayland.keybindings switch-to-session-12 ['<Primary><Alt>F12']
org.gnome.desktop.wm.keybindings panel-main-menu ['<Alt>F1']
org.gnome.desktop.wm.keybindings toggle-maximized ['<Alt>F10']
```

> 該設定是「`org.cinnamon.desktop.keybindings.wm switch-to-workspace-up ['<Control><Alt>Up', '<Alt>F1']`」這一行。

所以我們可以執行下面指令，來修改綁定。

``` sh
gsettings set org.cinnamon.desktop.keybindings.wm switch-to-workspace-up "['<Control><Alt>Up']"
```

執行下面指令，觀看目前「設定值」。

``` sh
gsettings get org.cinnamon.desktop.keybindings.wm switch-to-workspace-up
```

顯示

```
['<Control><Alt>Up']
```

> 若是要恢復成「預設值」，則是執行下面指令

``` sh
gsettings reset org.cinnamon.desktop.keybindings.wm switch-to-workspace-up
```

或是執行下面指令

``` sh
gsettings set org.cinnamon.desktop.keybindings.wm switch-to-workspace-up "['<Control><Alt>Up', '<Alt>F1']"
```
