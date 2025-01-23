---
title: 設定「Hot Corner Action」
nav_order: 7050
has_children: true
parent: 如何
---


# 設定「Hot Corner Action」




## 主題

* [前提](#前提)
* [設定方式](#設定方式)
* [相關議題](#相關議題)




## 前提

> 執行下面指令，探索關於「`hotcorner`」的設定。

``` sh
gsettings list-recursively | grep 'hotcorner'
```

顯示如下

```
org.cinnamon hotcorner-layout ['expo:false:0', 'scale:false:0', 'scale:false:0', 'desktop:false:0']
```




## 設定方式

> 執行下面指令，綁定「滑鼠」移到「桌面四方角落」會「觸發的動作」。

> 左上, 右上, 左下, 右下

``` sh
gsettings set org.cinnamon hotcorner-layout "['expo:true:0', 'gnome-terminal:true:0', 'scale:true:0', 'desktop:true:0']"
```




## 相關議題

* [設定「主要」的「按鍵綁定」](https://samwhelp.github.io/note-about-linuxmint-cinnamon/read/howto/config-keybind/config-keybind-main.html)
* [設定「自訂」的「按鍵綁定」](https://samwhelp.github.io/note-about-linuxmint-cinnamon/read/howto/config-keybind/config-keybind-custom.html)
* [設定「Alt-Tab Switcher Keybind」](https://samwhelp.github.io/note-about-linuxmint-cinnamon/read/howto/config-alttab-switcher/config-alttab-switcher-keybind.html)
