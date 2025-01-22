---
title: 設定「Mouse Button Modifier」
nav_order: 7021
has_children: false
parent: 如何
---


# 設定「Mouse Button Modifier」




## 主題

* [前提](#前提)
* [調整設定指令](#調整設定指令)
* [相關議題](#相關議題)
* [相關應用](#相關應用)
* [相關連結](#相關連結)




## 前提

在「Cinnamon Desktop」，預設是將「Mouse Button Modifier」設定為「`Alt鍵`」。

可以執行下面指令，找到該設定。

``` sh
gsettings list-recursively | grep "'<Alt>'"
```


顯示類似如下

```
org.cinnamon.desktop.wm.preferences mouse-button-modifier '<Alt>'
org.cinnamon.desktop.wm.preferences mouse-button-zoom-modifier '<Alt>'
org.gnome.desktop.wm.preferences mouse-button-modifier '<Alt>'
```

> 該設定是「`org.cinnamon.desktop.wm.preferences mouse-button-modifier '<Alt>'`」這一行。

我個人慣用的「Mouse Button Modifier」是「`Win鍵`」。

所以以下我會調整成我順手的操作模式。




## 調整設定指令

執行下面指令，將「Mouse Button Modifier」設定「`Super鍵`」，也就是「`Win鍵`」。

``` sh
gsettings set org.cinnamon.desktop.wm.preferences mouse-button-modifier "'<Super>'"
```

執行下面指令，讓「Mouse Button Modifier」也可以搭配「滑鼠右鍵更改視窗大小」的功能。

``` sh
gsettings set org.cinnamon.desktop.wm.preferences resize-with-right-button true
```

執行上面兩個指令後，就可以[在視窗操作下面兩個動作](https://samwhelp.github.io/note-about-linuxmint-cinnamon/read/config/mousebind.html#視窗內容區塊)，

| 滑鼠按鍵組合                |  功能                   |
| --------------------------- | ----------------------- |
| `Win + [滑鼠左鍵按住拖曳]`  | 視窗移動                |
| `Win + [滑鼠右鍵按住拖曳]`  | 視窗更改大小            |


另外因為我慣用「`Win鍵`」的「按鍵組合」來操作一些「視窗動作」，

例如「`Win + q` => 視窗關閉」，「`Win + m` => 視窗最大化」。

在「Cinnamon Desktop」，預設按下「`Win鍵`」會觸發「顯示Menu」，

為了避免無謂的干擾，我會停用這個功能，

請參考『[停用按鍵綁定「Super_L」開啟「Menu」](https://samwhelp.github.io/note-about-linuxmint-cinnamon/read/howto/disable-keybind-open-menu.html)』這篇的說明。




## 相關議題

| 相關議題 |
| ------- |
| [滑鼠按鍵綁定](https://samwhelp.github.io/note-about-linuxmint-cinnamon/read/config/mousebind.html#視窗內容區塊) |
| [停用按鍵綁定「Super_L」開啟「Menu」](https://samwhelp.github.io/note-about-linuxmint-cinnamon/read/howto/disable-keybind-open-menu.html) |




## 相關應用

* Menu Applet 開發筆記 / [demo-mouse-button-modifier](https://samwhelp.github.io/note-about-menu-applet/read/demo/demo-mouse-button-modifier.html#cinnamon)




## 相關連結

* Arch Wiki / Cinnamon / [Resize windows by mouse](https://wiki.archlinux.org/title/cinnamon#Resize_windows_by_mouse)
* Arch Wiki / GNOME / [Resize windows by mouse](https://wiki.archlinux.org/title/GNOME#Resize_windows_by_mouse)
