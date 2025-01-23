---
title: 設定「主要」的「按鍵綁定」
nav_order: 7010
has_children: false
parent: 設定「按鍵綁定 (Keybind)」
grand_parent: 如何
---


# 設定「主要」的「按鍵綁定」




## 主題

* [前提](#前提)
* [設定範例](#設定範例)
* [統整](#統整)
* [範例腳本](#範例腳本)
* [相關案例](#相關案例)




## 前提

延續「[設定「按鍵綁定 (Keybind)」](https://samwhelp.github.io/note-about-linuxmint-cinnamon/read/howto/config-keybind.html)」這篇找到的設定，

以下紀錄我常用的「視窗操作按鍵綁定」來當作「[設定範例](#設定範例)」說明。




## 設定範例

* [Alt-Tab Switcher](#alt-tab-switcher)
* [Window / close](#window--close)
* [Window / toggle-maximized](#window--toggle-maximized)
* [Window / toggle-fullscreen](#window--toggle-fullscreen)
* [Window / show-desktop](#window--show-desktop)
* [Window / begin-move](#window--begin-move)
* [Window / begin-resize](#window--begin-resize)
* [Workspace / switch-to-workspace-left](#overview--switch-to-workspace-left)
* [Workspace / switch-to-workspace-right](#overview--switch-to-workspace-right)
* [Overview / switch-to-workspace-up](#overview--switch-to-workspace-up)
* [Overview / switch-to-workspace-down](#overview--switch-to-workspace-down)
* [Screenshot](#screenshot)
* [統整](#統整)



## Alt-Tab Switcher

> 請參考另一篇『[設定「Alt-Tab Switcher Keybind」](https://samwhelp.github.io/note-about-linuxmint-cinnamon/read/howto/config-alttab-switcher/config-alttab-switcher-keybind.html)』的「設定說明」。




## Window / close

大部份的桌面環境，預設是綁定「`Alt + F4`」來「關閉視窗」。

```
org.cinnamon.desktop.keybindings.wm close ['<Alt>F4']
```

我個人慣用的是綁定「`Win + q`」來「關閉視窗」。


> 執行下面指令，綁定「`Win + q`」來「關閉視窗」。

``` sh
gsettings set org.cinnamon.desktop.keybindings.wm close "['<Super>q']"
```


> 或是也可以執行下面指令，綁定「`Win + q`」來「關閉視窗」，並且也保留原來的「`Alt + F4`」綁定。

``` sh
gsettings set org.cinnamon.desktop.keybindings.wm close "['<Super>q', '<Alt>F4']"
```

> 上面的範例，表示一個功能，可以有多重綁定。




## Window / toggle-maximized

> 執行下面指令，綁定「`Win + w`」來「切換視窗最大化」。

``` sh
gsettings set org.cinnamon.desktop.keybindings.wm toggle-maximized "['<Super>w']"
```




## Window / toggle-fullscreen

> 執行下面指令，綁定「`Win + f`」來「切換視窗全螢幕」。

``` sh
gsettings set org.cinnamon.desktop.keybindings.wm toggle-fullscreen "['<Super>f']"
```






## Window / show-desktop

> 執行下面指令，綁定「`Win + d`」來「切換顯示桌面」。

``` sh
gsettings set org.cinnamon.desktop.keybindings.wm show-desktop "['<Super>d']"
```

> 在「Linux Mint Cinnamon Desktop」，預設就是綁定「`Win + d`」來「切換顯示桌面」






## Window / begin-move

> 執行下面指令，綁定「`Win + e`」來切換到「視窗開始移動」狀態。

``` sh
gsettings set org.cinnamon.desktop.keybindings.wm begin-move "['<Super>e']"
```

> 原本「`Win + e`」已經有綁定功能

```
org.cinnamon.desktop.keybindings.media-keys home ['<Super>e', 'XF86Explorer']
```

> 所以執行下面指令，解決「按鍵綁定衝突」

``` sh
gsettings set org.cinnamon.desktop.keybindings.media-keys home "['XF86Explorer']"
```




## Window / begin-resize

> 執行下面指令，綁定「`Win + r`」來切換到「視窗開始更改大小」狀態。

``` sh
gsettings set org.cinnamon.desktop.keybindings.wm begin-resize "['<Super>r']"
```


> 關於「[begin-move](#window--begin-move)」和「[begin-resize](#window--begin-resize)」，可以對照另一篇『[設定「Mouse Button Modifier」](https://samwhelp.github.io/note-about-linuxmint-cinnamon/read/howto/config-mouse-button-modifier.html)』提到的用法。




## Workspace / switch-to-workspace-left

> 原本預設的綁定如下

```
org.cinnamon.desktop.keybindings.wm switch-to-workspace-left ['<Control><Alt>Left']
```

> 執行下面指令，綁定「`Alt + a`」來切換到「`上一個工作空間`」，也保留原來的「`Ctrl + Alt + Left`」。

``` sh
gsettings set org.cinnamon.desktop.keybindings.wm switch-to-workspace-left  "['<Alt>a', '<Control><Alt>Left']"
```




## Workspace / switch-to-workspace-right

> 原本預設的綁定如下

```
org.cinnamon.desktop.keybindings.wm switch-to-workspace-right ['<Control><Alt>Right']
```

> 執行下面指令，綁定「`Alt + s`」來切換到「`下一個工作空間`」，也保留原來的「`Ctrl + Alt + Right`」。

``` sh
gsettings set org.cinnamon.desktop.keybindings.wm switch-to-workspace-right  "['<Alt>s', '<Control><Alt>Right']"
```




## Overview / switch-to-workspace-up

> 原本預設的綁定如下（在『[停用按鍵綁定「Super_L」開啟「Menu」](https://samwhelp.github.io/note-about-linuxmint-cinnamon/read/howto/disable-keybind-open-menu.html#衝突綁定)』）這篇有提到這個設定。

```
org.cinnamon.desktop.keybindings.wm switch-to-workspace-up ['<Control><Alt>Up', '<Alt>F1']
```

> 執行下面指令，綁定「`Win + grave`」來切換到「所有工作空間預覽」，也保留原來的「`Ctrl + Alt + Up`」。

``` sh
gsettings set org.cinnamon.desktop.keybindings.wm switch-to-workspace-up "['<Super>grave', '<Control><Alt>Up']"
```

> 注意「`Win + grave`」會跟「`Grouped window list / Hot keys / Global hotkey for cycling through thumbnail menus`」衝突綁定，記得要設定移除。




## Overview / switch-to-workspace-down

> 原本預設的綁定如下

```
org.cinnamon.desktop.keybindings.wm switch-to-workspace-down ['<Control><Alt>Down']
```

> 執行下面指令，綁定「`Win + Tab`」來切換到「目前工作空間/所有視窗預覽」，也保留原來的「`Ctrl + Alt + Down`」。

``` sh
gsettings set org.cinnamon.desktop.keybindings.wm switch-to-workspace-down "['<Super>Tab', '<Control><Alt>Down']"
```




## Window / Tiling Move

> 原本預設的綁定如下

```
org.cinnamon.desktop.keybindings.wm push-tile-down ['<Super>Down']
org.cinnamon.desktop.keybindings.wm push-tile-left ['<Super>Left']
org.cinnamon.desktop.keybindings.wm push-tile-right ['<Super>Right']
org.cinnamon.desktop.keybindings.wm push-tile-up ['<Super>Up']
```

> 並不需要修改，設定參考指令如下

``` sh

##
## ## Window / Tiling Move
##

gsettings set org.cinnamon.desktop.keybindings.wm push-tile-down "['<Super>Down']"

gsettings set org.cinnamon.desktop.keybindings.wm push-tile-left "['<Super>Left']"

gsettings set org.cinnamon.desktop.keybindings.wm push-tile-right "['<Super>Right']"

gsettings set org.cinnamon.desktop.keybindings.wm push-tile-up "['<Super>Up']"

```


## Screenshot

> 執行下面指令，探索關於「`screenshot`」的「按鍵綁定」設定

``` sh
gsettings list-recursively | grep org.cinnamon.desktop.keybindings.media-keys | grep screenshot
```

顯示

```
org.cinnamon.desktop.keybindings.media-keys area-screenshot ['<Shift>Print']
org.cinnamon.desktop.keybindings.media-keys area-screenshot-clip ['<Control><Shift>Print']
org.cinnamon.desktop.keybindings.media-keys screenshot ['Print']
org.cinnamon.desktop.keybindings.media-keys screenshot-clip ['<Control>Print']
org.cinnamon.desktop.keybindings.media-keys window-screenshot ['<Alt>Print']
org.cinnamon.desktop.keybindings.media-keys window-screenshot-clip ['<Control><Alt>Print']
```


> 執行下面指令，修改關於「`screenshot`」的「按鍵綁定」設定

``` sh

##
## ## Screenshot
##

gsettings set org.cinnamon.desktop.keybindings.media-keys screenshot "['Print']"

gsettings set org.cinnamon.desktop.keybindings.media-keys screenshot-clip "['<Shift>Print']"


##
## ## Screenshot / Window
##

gsettings set org.cinnamon.desktop.keybindings.media-keys window-screenshot "['<Super>Print']"

gsettings set org.cinnamon.desktop.keybindings.media-keys window-screenshot-clip "['<Alt><Super>Print']"


##
## ## Screenshot / Area
##

gsettings set org.cinnamon.desktop.keybindings.media-keys area-screenshot "['<Control>Print']"

gsettings set org.cinnamon.desktop.keybindings.media-keys area-screenshot-clip "['<Alt><Control>Print']"


```

## 統整

> 統整以上提到的綁定

``` sh

##
## ## Fix
##

gsettings set org.cinnamon.desktop.keybindings.media-keys home "['XF86Explorer']"

gsettings set org.cinnamon.desktop.keybindings show-desklets "[]"


##
## ## Window
##

gsettings set org.cinnamon.desktop.keybindings.wm close "['<Super>q']"

gsettings set org.cinnamon.desktop.keybindings.wm toggle-maximized "['<Super>w']"

gsettings set org.cinnamon.desktop.keybindings.wm toggle-fullscreen "['<Super>f']"

gsettings set org.cinnamon.desktop.keybindings.wm show-desktop "['<Super>d']"

gsettings set org.cinnamon.desktop.keybindings.wm begin-move "['<Super>e']"

gsettings set org.cinnamon.desktop.keybindings.wm begin-resize "['<Super>r']"


##
## ## Window / Switch
##

gsettings set org.cinnamon.desktop.keybindings.wm switch-windows-backward "['<Super>a']"

gsettings set org.cinnamon.desktop.keybindings.wm switch-windows "['<Super>s']"


##
## ## Workspace / Switch
##

gsettings set org.cinnamon.desktop.keybindings.wm switch-to-workspace-left  "['<Alt>a', '<Control><Alt>Left']"

gsettings set org.cinnamon.desktop.keybindings.wm switch-to-workspace-right  "['<Alt>s', '<Control><Alt>Right']"


##
## ## Overview / Switch
##

gsettings set org.cinnamon.desktop.keybindings.wm switch-to-workspace-up "['<Super>grave', '<Control><Alt>Up']"

gsettings set org.cinnamon.desktop.keybindings.wm switch-to-workspace-down "['<Super>Tab', '<Control><Alt>Down']"


##
## ## Window / Tiling Move
##

gsettings set org.cinnamon.desktop.keybindings.wm push-tile-down "['<Super>Down']"

gsettings set org.cinnamon.desktop.keybindings.wm push-tile-left "['<Super>Left']"

gsettings set org.cinnamon.desktop.keybindings.wm push-tile-right "['<Super>Right']"

gsettings set org.cinnamon.desktop.keybindings.wm push-tile-up "['<Super>Up']"


##
## ## Screenshot
##

gsettings set org.cinnamon.desktop.keybindings.media-keys screenshot "['Print']"

gsettings set org.cinnamon.desktop.keybindings.media-keys screenshot-clip "['<Shift>Print']"


##
## ## Screenshot / Window
##

gsettings set org.cinnamon.desktop.keybindings.media-keys window-screenshot "['<Super>Print']"

gsettings set org.cinnamon.desktop.keybindings.media-keys window-screenshot-clip "['<Alt><Super>Print']"


##
## ## Screenshot / Area
##

gsettings set org.cinnamon.desktop.keybindings.media-keys area-screenshot "['<Control>Print']"

gsettings set org.cinnamon.desktop.keybindings.media-keys area-screenshot-clip "['<Alt><Control>Print']"


```


> 另外關於「Workspace」，我會做如下的額外設定


``` sh

gsettings set org.cinnamon.desktop.wm.preferences num-workspaces 5

gsettings set org.cinnamon.desktop.wm.preferences workspace-names "['File', 'Edit', 'Web', 'Term', 'Misc']"

gsettings set org.cinnamon.muffin dynamic-workspaces false

gsettings set org.cinnamon.muffin workspace-cycle true

```




## 範例腳本

* [範例腳本](https://github.com/samwhelp/note-about-linuxmint-cinnamon/tree/gh-pages/_demo/scripts/cinnamon-keybind)




## 相關案例

* [cinnamon-keybind-main](https://github.com/samwhelp/note-about-ubuntu/blob/gh-pages/_demo/adjustment/de/cinnamon/part/cinnamon-keybind-main/config-install.sh)
* [/usr/share/glib-2.0/schemas/50_cinnamon-keybind-main.gschema.override](https://github.com/samwhelp/lika-live-build-respin-cinnamon/blob/main/asset/overlay/usr/share/glib-2.0/schemas/50_cinnamon-keybind-main.gschema.override)
