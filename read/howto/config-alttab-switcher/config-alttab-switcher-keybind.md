---
title: 設定「Alt-Tab Switcher Keybind」
nav_order: 7020
has_children: false
parent: 設定「Alt-Tab Switcher」
grand_parent: 如何
---


# 設定「Alt-Tab Switcher Keybind」




## 主題

* [前提](#前提)
* [檢查按鍵綁定衝突](#檢查按鍵綁定衝突)
* [設定方式](#設定方式)




## 前提

> 執行下面指令，探索關於「`<Alt>Tab`」的設定

``` sh
gsettings list-recursively | grep "<Alt>Tab"
```

顯示

```
org.cinnamon.desktop.keybindings.wm switch-panels ['<Control><Alt>Tab']
org.cinnamon.desktop.keybindings.wm switch-panels-backward ['<Shift><Control><Alt>Tab']
org.cinnamon.desktop.keybindings.wm switch-windows ['<Alt>Tab']
org.cinnamon.desktop.keybindings.wm switch-windows-backward ['<Shift><Alt>Tab']
org.gnome.desktop.wm.keybindings switch-applications ['<Super>Tab', '<Alt>Tab']
org.gnome.desktop.wm.keybindings switch-applications-backward ['<Shift><Super>Tab', '<Shift><Alt>Tab']
org.gnome.desktop.wm.keybindings switch-panels ['<Control><Alt>Tab']
org.gnome.desktop.wm.keybindings switch-panels-backward ['<Shift><Control><Alt>Tab']
```


> 執行下面指令，探索關於「`'<Alt>Tab'`」的設定

``` sh
gsettings list-recursively | grep "'<Alt>Tab'"
```

顯示

```
org.cinnamon.desktop.keybindings.wm switch-windows ['<Alt>Tab']
org.gnome.desktop.wm.keybindings switch-applications ['<Super>Tab', '<Alt>Tab']
```

> 從上面可以了解到，我們這裡聚焦的設定如下

```
org.cinnamon.desktop.keybindings.wm switch-windows ['<Alt>Tab']
org.cinnamon.desktop.keybindings.wm switch-windows-backward ['<Shift><Alt>Tab']
```




## 檢查按鍵綁定衝突

這裡我們期望綁定「`Super + a`」和「`Super + s`」，所以需要事先檢查，是否已有綁定。

> 執行下面指令，探索是否已經有綁定「`Super + a`」的「按鍵綁定」。

``` sh
gsettings list-recursively | grep -i '<Super>a'
```

顯示

``` sh
org.gnome.desktop.wm.keybindings switch-group ['<Super>Above_Tab', '<Alt>Above_Tab']
org.gnome.desktop.wm.keybindings switch-group-backward ['<Shift><Super>Above_Tab', '<Shift><Alt>Above_Tab']
```



> 執行下面指令，探索是否已經有綁定「`Super + s`」的「按鍵綁定」。

``` sh
gsettings list-recursively | grep -i '<Super>a'
```

顯示

``` sh
org.cinnamon.desktop.keybindings show-desklets ['<Super>s']
org.cinnamon.desktop.keybindings.media-keys screenreader ['<Alt><Super>s']
org.gnome.desktop.wm.keybindings switch-input-source ['<Super>space', 'XF86Keyboard']
org.gnome.desktop.wm.keybindings switch-input-source-backward ['<Shift><Super>space', '<Shift>XF86Keyboard']
org.gnome.settings-daemon.plugins.media-keys screenreader ['<Alt><Super>s']
```

> 找到已經有綁定「`org.cinnamon.desktop.keybindings show-desklets ['<Super>s']`」。

所以我們可以執行下面指令，將這個綁定移除。

``` sh
gsettings set org.cinnamon.desktop.keybindings show-desklets "[]"
```

執行下面指令，觀看目前的「設定值」

``` sh
gsettings get org.cinnamon.desktop.keybindings show-desklets
```

顯示

```
@as []
```




## 設定方式

> 執行下面指令，分別綁定「`Super + a`」和「`Super + s`」

``` sh

gsettings set org.cinnamon.desktop.keybindings.wm switch-windows-backward "['<Super>a']"

gsettings set org.cinnamon.desktop.keybindings.wm switch-windows "['<Super>s']"

```


> 或是執行下面指令，保存原來的綁定，分別加入綁定「`Super + a`」和「`Super + s`」

``` sh

gsettings set org.cinnamon.desktop.keybindings.wm switch-windows-backward "['<Super>a', '<Shift><Alt>Tab']"

gsettings set org.cinnamon.desktop.keybindings.wm switch-windows "['<Super>s', '<Alt>Tab']"

```
