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




## 前提

延續「[設定「按鍵綁定 (Keybind)」](https://samwhelp.github.io/note-about-linuxmint-cinnamon/read/howto/config-keybind.html)」這篇找到的設定，

以下紀錄我常用的「視窗操作按鍵綁定」來當作「[設定範例](#設定範例)」說明。




## 設定範例

* [Alt-Tab Switcher](#alt-tab-switcher)
* [ Window / close](##window--close)
* [ Window / toggle-maximized](##window--toggle-maximized)
* [ Window / toggle-fullscreen](##window--toggle-fullscreen)
* [ Window / show-desktop](##window--show-desktop)
* [ Window / begin-move](##window--begin-move)
* [ Window / begin-resize](##window--begin-resize)




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
