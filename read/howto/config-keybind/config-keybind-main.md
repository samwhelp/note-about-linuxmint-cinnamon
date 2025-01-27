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

> 要注意的是，以下只是單就個別項目做說明，有些綁定可能會跟目前既有的綁定衝突，所以要設定完整，還是要做統整的設定
以下紀錄並不全面。




## 設定範例

* [Alt-Tab Switcher](#alt-tab-switcher)
* [Window / Close](#window--close)
* [Window / Toggle Maximized](#window--toggle-maximized)
* [Window / Toggle Fullscreen](#window--toggle-fullscreen)
* [Window / Show Desktop](#window--show-desktop)
* [Window / Begin Move](#window--begin-move)
* [Window / Begin Resize](#window--begin-resize)
* [Workspace / Previous](#workspace--previous)
* [Workspace / Next](#workspace--next)
* [Overview / Expo](#overview--expo)
* [Overview / Scale](#overview--scale)
* [Window / Tiling Move](#window--tiling-move)
* [Screenshot](#screenshot)
* [統整](#統整)




## Alt-Tab Switcher

> 請參考另一篇『[設定「Alt-Tab Switcher Keybind」](https://samwhelp.github.io/note-about-linuxmint-cinnamon/read/howto/config-alttab-switcher/config-alttab-switcher-keybind.html)』的「設定說明」。




## Window / Close

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




## Window / Toggle Maximized

> 執行下面指令，綁定「`Win + w`」來「切換視窗最大化」。

``` sh
gsettings set org.cinnamon.desktop.keybindings.wm toggle-maximized "['<Super>w']"
```




## Window / Toggle Fullscreen

> 執行下面指令，綁定「`Win + f`」來「切換視窗全螢幕」。

``` sh
gsettings set org.cinnamon.desktop.keybindings.wm toggle-fullscreen "['<Super>f']"
```






## Window / Show Desktop

> 執行下面指令，綁定「`Win + d`」來「切換顯示桌面」。

``` sh
gsettings set org.cinnamon.desktop.keybindings.wm show-desktop "['<Super>d']"
```

> 在「Linux Mint Cinnamon Desktop」，預設就是綁定「`Win + d`」來「切換顯示桌面」






## Window / Begin Move

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




## Window / Begin Resize

> 執行下面指令，綁定「`Win + r`」來切換到「視窗開始更改大小」狀態。

``` sh
gsettings set org.cinnamon.desktop.keybindings.wm begin-resize "['<Super>r']"
```


> 關於「[begin-move](#window--begin-move)」和「[begin-resize](#window--begin-resize)」，可以對照另一篇『[設定「Mouse Button Modifier」](https://samwhelp.github.io/note-about-linuxmint-cinnamon/read/howto/config-mouse-button-modifier.html)』提到的用法。




## Workspace / Previous

> 原本預設的綁定如下

```
org.cinnamon.desktop.keybindings.wm switch-to-workspace-left ['<Control><Alt>Left']
```

> 執行下面指令，綁定「`Alt + a`」來切換到「`上一個工作空間`」，也保留原來的「`Ctrl + Alt + Left`」。

``` sh
gsettings set org.cinnamon.desktop.keybindings.wm switch-to-workspace-left  "['<Alt>a', '<Control><Alt>Left']"
```




## Workspace / Next

> 原本預設的綁定如下

```
org.cinnamon.desktop.keybindings.wm switch-to-workspace-right ['<Control><Alt>Right']
```

> 執行下面指令，綁定「`Alt + s`」來切換到「`下一個工作空間`」，也保留原來的「`Ctrl + Alt + Right`」。

``` sh
gsettings set org.cinnamon.desktop.keybindings.wm switch-to-workspace-right  "['<Alt>s', '<Control><Alt>Right']"
```




## Overview / Expo

> 原本預設的綁定如下（在『[停用按鍵綁定「Super_L」開啟「Main Menu」](https://samwhelp.github.io/note-about-linuxmint-cinnamon/read/howto/disable-keybind-open-main-menu.html#綁定衝突)』）這篇有提到這個設定。

```
org.cinnamon.desktop.keybindings.wm switch-to-workspace-up ['<Control><Alt>Up', '<Alt>F1']
```

> 執行下面指令，綁定「`Win + grave`」來切換到「所有工作空間概覽」，也保留原來的「`Ctrl + Alt + Up`」。

``` sh
gsettings set org.cinnamon.desktop.keybindings.wm switch-to-workspace-up "['<Super>grave', '<Control><Alt>Up']"
```

> 注意「`Win + grave`」會跟「`Grouped window list / Hot keys / Global hotkey for cycling through thumbnail menus`」綁定衝突，記得要設定移除。




## Overview / Scale

> 原本預設的綁定如下

```
org.cinnamon.desktop.keybindings.wm switch-to-workspace-down ['<Control><Alt>Down']
```

> 執行下面指令，綁定「`Win + Tab`」來切換到「目前工作空間的所有視窗概覽」，也保留原來的「`Ctrl + Alt + Down`」。

``` sh
gsettings set org.cinnamon.desktop.keybindings.wm switch-to-workspace-down "['<Super>Tab', '<Control><Alt>Down']"
```


| 方位        | 按鍵           | 功能                    |
| ----------- | -------------- | ----------------------- |
| 上 (Up)     | `Win + grave`  | `Overview / Expo`       |
| 下 (Down)   | `Win + Tab`    | `Overview / Scale`      |
| 左 (Left)   | `Alt + a`      | `Workspace / Previous`  |
| 右 (Right)  | `Alt + s`      | `Workspace / Next`      |
| 左 (Left)   | `Win + a`      | `Window / Previous`     |
| 右 (Right)  | `Win + s`      | `Window / Next`         |

> 關於「grave」指是「`」，在「Tab鍵」上方的那個「鍵盤按鍵」。

> 關於「`Overview / Expo`」，我有設定「`Hot corner / 左上`」觸發。

> 關於「`Overview / Scale`」，我有設定「`Hot corner / 左下`」觸發。

> 可以對照『[設定「Hot Corner Action」](https://samwhelp.github.io/note-about-linuxmint-cinnamon/read/howto/config-hot-corner-action.html)』這篇的說明。

> `Win` for `Window`

> `Alt` for `Workspace`




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

> `Super` for `Window`

> `Control` for `Area`




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
