---
title: 設定「按鍵綁定 (Keybind)」
nav_order: 7030
has_children: true
parent: 如何
---


# 設定「按鍵綁定 (Keybind)」




## 主題

* [前提](#前提)
* [設定方式](#設定方式)
* [相關議題](#相關議題)




## 前提

> 執行下面指令，探索關於「`keybind`」的設定。

``` sh
gsettings list-recursively | grep 'keybind'
```

顯示如下 (有很多，只列前面幾行)

```
org.cinnamon.desktop.keybindings custom-list @as []
org.cinnamon.desktop.keybindings looking-glass-keybinding ['<Super>l']
org.cinnamon.desktop.keybindings magnifier-zoom-in ['<Alt><Super>equal']
org.cinnamon.desktop.keybindings magnifier-zoom-out ['<Alt><Super>minus']

...

```


> 執行下面指令，探索關於「`org.cinnamon.desktop.keybindings`」的設定。

``` sh
gsettings list-recursively | grep 'org.cinnamon.desktop.keybindings'
```

顯示

```
org.cinnamon.desktop.keybindings custom-list @as []
org.cinnamon.desktop.keybindings looking-glass-keybinding ['<Super>l']
org.cinnamon.desktop.keybindings magnifier-zoom-in ['<Alt><Super>equal']
org.cinnamon.desktop.keybindings magnifier-zoom-out ['<Alt><Super>minus']
org.cinnamon.desktop.keybindings pointer-next-monitor @as []
org.cinnamon.desktop.keybindings pointer-previous-monitor @as []
org.cinnamon.desktop.keybindings show-desklets ['<Super>s']
org.cinnamon.desktop.keybindings.media-keys area-screenshot ['<Shift>Print']
org.cinnamon.desktop.keybindings.media-keys area-screenshot-clip ['<Control><Shift>Print']
org.cinnamon.desktop.keybindings.media-keys audio-forward ['XF86AudioForward']
org.cinnamon.desktop.keybindings.media-keys audio-random ['XF86AudioRandomPlay']
org.cinnamon.desktop.keybindings.media-keys audio-repeat ['XF86AudioRepeat']
org.cinnamon.desktop.keybindings.media-keys audio-rewind ['XF86AudioRewind']
org.cinnamon.desktop.keybindings.media-keys battery ['XF86Battery']
org.cinnamon.desktop.keybindings.media-keys calculator ['XF86Calculator']
org.cinnamon.desktop.keybindings.media-keys decrease-text-size ['']
org.cinnamon.desktop.keybindings.media-keys eject ['XF86Eject']
org.cinnamon.desktop.keybindings.media-keys email ['XF86Mail']
org.cinnamon.desktop.keybindings.media-keys help ['']
org.cinnamon.desktop.keybindings.media-keys hibernate ['XF86Suspend', 'XF86Hibernate']
org.cinnamon.desktop.keybindings.media-keys home ['<Super>e', 'XF86Explorer']
org.cinnamon.desktop.keybindings.media-keys increase-text-size ['']
org.cinnamon.desktop.keybindings.media-keys kbd-brightness-down ['XF86KbdBrightnessDown']
org.cinnamon.desktop.keybindings.media-keys kbd-brightness-toggle ['XF86KbdLightOnOff']
org.cinnamon.desktop.keybindings.media-keys kbd-brightness-up ['XF86KbdBrightnessUp']
org.cinnamon.desktop.keybindings.media-keys logout ['<Control><Alt>Delete']
org.cinnamon.desktop.keybindings.media-keys media ['XF86AudioMedia']
org.cinnamon.desktop.keybindings.media-keys mic-mute ['XF86AudioMicMute']
org.cinnamon.desktop.keybindings.media-keys mute-quiet ['<Alt>XF86AudioMute']
org.cinnamon.desktop.keybindings.media-keys next ['XF86AudioNext']
org.cinnamon.desktop.keybindings.media-keys on-screen-keyboard ['']
org.cinnamon.desktop.keybindings.media-keys pause ['XF86AudioPause']
org.cinnamon.desktop.keybindings.media-keys play ['XF86AudioPlay']
org.cinnamon.desktop.keybindings.media-keys previous ['XF86AudioPrev']
org.cinnamon.desktop.keybindings.media-keys restart-cinnamon ['<Control><Alt>Escape']
org.cinnamon.desktop.keybindings.media-keys screen-brightness-down ['XF86MonBrightnessDown']
org.cinnamon.desktop.keybindings.media-keys screen-brightness-up ['XF86MonBrightnessUp']
org.cinnamon.desktop.keybindings.media-keys screenreader ['<Alt><Super>s']
org.cinnamon.desktop.keybindings.media-keys screensaver ['<Control><Alt>l', 'XF86ScreenSaver']
org.cinnamon.desktop.keybindings.media-keys screenshot ['Print']
org.cinnamon.desktop.keybindings.media-keys screenshot-clip ['<Control>Print']
org.cinnamon.desktop.keybindings.media-keys search ['XF86Search']
org.cinnamon.desktop.keybindings.media-keys shutdown ['<Control><Alt>End', 'XF86PowerOff']
org.cinnamon.desktop.keybindings.media-keys stop ['XF86AudioStop']
org.cinnamon.desktop.keybindings.media-keys suspend ['XF86Sleep']
org.cinnamon.desktop.keybindings.media-keys terminal ['<Primary><Alt>t']
org.cinnamon.desktop.keybindings.media-keys toggle-contrast ['']
org.cinnamon.desktop.keybindings.media-keys touchpad-off ['XF86TouchpadOff']
org.cinnamon.desktop.keybindings.media-keys touchpad-on ['XF86TouchpadOn']
org.cinnamon.desktop.keybindings.media-keys touchpad-toggle ['XF86TouchpadToggle']
org.cinnamon.desktop.keybindings.media-keys video-outputs @as []
org.cinnamon.desktop.keybindings.media-keys video-rotation @as []
org.cinnamon.desktop.keybindings.media-keys video-rotation-lock ['<Super>o']
org.cinnamon.desktop.keybindings.media-keys volume-down ['XF86AudioLowerVolume']
org.cinnamon.desktop.keybindings.media-keys volume-down-quiet ['<Alt>XF86AudioLowerVolume']
org.cinnamon.desktop.keybindings.media-keys volume-mute ['XF86AudioMute']
org.cinnamon.desktop.keybindings.media-keys volume-up ['XF86AudioRaiseVolume']
org.cinnamon.desktop.keybindings.media-keys volume-up-quiet ['<Alt>XF86AudioRaiseVolume']
org.cinnamon.desktop.keybindings.media-keys window-screenshot ['<Alt>Print']
org.cinnamon.desktop.keybindings.media-keys window-screenshot-clip ['<Control><Alt>Print']
org.cinnamon.desktop.keybindings.media-keys www ['XF86WWW']
org.cinnamon.desktop.keybindings.wm activate-window-menu ['<Alt>space']
org.cinnamon.desktop.keybindings.wm begin-move ['<Alt>F7']
org.cinnamon.desktop.keybindings.wm begin-resize ['<Alt>F8']
org.cinnamon.desktop.keybindings.wm close ['<Alt>F4']
org.cinnamon.desktop.keybindings.wm decrease-opacity @as []
org.cinnamon.desktop.keybindings.wm increase-opacity @as []
org.cinnamon.desktop.keybindings.wm lower @as []
org.cinnamon.desktop.keybindings.wm maximize @as []
org.cinnamon.desktop.keybindings.wm maximize-horizontally @as []
org.cinnamon.desktop.keybindings.wm maximize-vertically @as []
org.cinnamon.desktop.keybindings.wm minimize @as []
org.cinnamon.desktop.keybindings.wm move-to-center @as []
org.cinnamon.desktop.keybindings.wm move-to-corner-ne @as []
org.cinnamon.desktop.keybindings.wm move-to-corner-nw @as []
org.cinnamon.desktop.keybindings.wm move-to-corner-se @as []
org.cinnamon.desktop.keybindings.wm move-to-corner-sw @as []
org.cinnamon.desktop.keybindings.wm move-to-monitor-down ['<Super><Shift>Down']
org.cinnamon.desktop.keybindings.wm move-to-monitor-left ['<Super><Shift>Left']
org.cinnamon.desktop.keybindings.wm move-to-monitor-right ['<Super><Shift>Right']
org.cinnamon.desktop.keybindings.wm move-to-monitor-up ['<Super><Shift>Up']
org.cinnamon.desktop.keybindings.wm move-to-side-e @as []
org.cinnamon.desktop.keybindings.wm move-to-side-n @as []
org.cinnamon.desktop.keybindings.wm move-to-side-s @as []
org.cinnamon.desktop.keybindings.wm move-to-side-w @as []
org.cinnamon.desktop.keybindings.wm move-to-workspace-1 @as []
org.cinnamon.desktop.keybindings.wm move-to-workspace-10 @as []
org.cinnamon.desktop.keybindings.wm move-to-workspace-11 @as []
org.cinnamon.desktop.keybindings.wm move-to-workspace-12 @as []
org.cinnamon.desktop.keybindings.wm move-to-workspace-2 @as []
org.cinnamon.desktop.keybindings.wm move-to-workspace-3 @as []
org.cinnamon.desktop.keybindings.wm move-to-workspace-4 @as []
org.cinnamon.desktop.keybindings.wm move-to-workspace-5 @as []
org.cinnamon.desktop.keybindings.wm move-to-workspace-6 @as []
org.cinnamon.desktop.keybindings.wm move-to-workspace-7 @as []
org.cinnamon.desktop.keybindings.wm move-to-workspace-8 @as []
org.cinnamon.desktop.keybindings.wm move-to-workspace-9 @as []
org.cinnamon.desktop.keybindings.wm move-to-workspace-down ['<Control><Shift><Alt>Down']
org.cinnamon.desktop.keybindings.wm move-to-workspace-left ['<Control><Shift><Alt>Left']
org.cinnamon.desktop.keybindings.wm move-to-workspace-new @as []
org.cinnamon.desktop.keybindings.wm move-to-workspace-right ['<Control><Shift><Alt>Right']
org.cinnamon.desktop.keybindings.wm move-to-workspace-up ['<Control><Shift><Alt>Up']
org.cinnamon.desktop.keybindings.wm panel-run-dialog ['<Alt>F2']
org.cinnamon.desktop.keybindings.wm push-snap-down @as []
org.cinnamon.desktop.keybindings.wm push-snap-left @as []
org.cinnamon.desktop.keybindings.wm push-snap-right @as []
org.cinnamon.desktop.keybindings.wm push-snap-up @as []
org.cinnamon.desktop.keybindings.wm push-tile-down ['<Super>Down']
org.cinnamon.desktop.keybindings.wm push-tile-left ['<Super>Left']
org.cinnamon.desktop.keybindings.wm push-tile-right ['<Super>Right']
org.cinnamon.desktop.keybindings.wm push-tile-up ['<Super>Up']
org.cinnamon.desktop.keybindings.wm raise @as []
org.cinnamon.desktop.keybindings.wm raise-or-lower @as []
org.cinnamon.desktop.keybindings.wm rotate-monitor ['XF86RotateWindows']
org.cinnamon.desktop.keybindings.wm set-spew-mark @as []
org.cinnamon.desktop.keybindings.wm show-desktop ['<Super>d']
org.cinnamon.desktop.keybindings.wm switch-group ['<Alt>Above_Tab']
org.cinnamon.desktop.keybindings.wm switch-group-backward ['<Shift><Alt>Above_Tab']
org.cinnamon.desktop.keybindings.wm switch-monitor ['<Super>p', 'XF86Display']
org.cinnamon.desktop.keybindings.wm switch-panels ['<Control><Alt>Tab']
org.cinnamon.desktop.keybindings.wm switch-panels-backward ['<Shift><Control><Alt>Tab']
org.cinnamon.desktop.keybindings.wm switch-to-workspace-1 @as []
org.cinnamon.desktop.keybindings.wm switch-to-workspace-10 @as []
org.cinnamon.desktop.keybindings.wm switch-to-workspace-11 @as []
org.cinnamon.desktop.keybindings.wm switch-to-workspace-12 @as []
org.cinnamon.desktop.keybindings.wm switch-to-workspace-2 @as []
org.cinnamon.desktop.keybindings.wm switch-to-workspace-3 @as []
org.cinnamon.desktop.keybindings.wm switch-to-workspace-4 @as []
org.cinnamon.desktop.keybindings.wm switch-to-workspace-5 @as []
org.cinnamon.desktop.keybindings.wm switch-to-workspace-6 @as []
org.cinnamon.desktop.keybindings.wm switch-to-workspace-7 @as []
org.cinnamon.desktop.keybindings.wm switch-to-workspace-8 @as []
org.cinnamon.desktop.keybindings.wm switch-to-workspace-9 @as []
org.cinnamon.desktop.keybindings.wm switch-to-workspace-down ['<Control><Alt>Down']
org.cinnamon.desktop.keybindings.wm switch-to-workspace-left ['<Control><Alt>Left']
org.cinnamon.desktop.keybindings.wm switch-to-workspace-right ['<Control><Alt>Right']
org.cinnamon.desktop.keybindings.wm switch-to-workspace-up ['<Control><Alt>Up', '<Alt>F1']
org.cinnamon.desktop.keybindings.wm switch-windows ['<Alt>Tab']
org.cinnamon.desktop.keybindings.wm switch-windows-backward ['<Shift><Alt>Tab']
org.cinnamon.desktop.keybindings.wm tab-popup-cancel @as []
org.cinnamon.desktop.keybindings.wm tab-popup-select @as []
org.cinnamon.desktop.keybindings.wm toggle-above @as []
org.cinnamon.desktop.keybindings.wm toggle-fullscreen @as []
org.cinnamon.desktop.keybindings.wm toggle-maximized ['<Alt>F10']
org.cinnamon.desktop.keybindings.wm toggle-on-all-workspaces @as []
org.cinnamon.desktop.keybindings.wm toggle-recording ['<Control><Shift><Alt>r']
org.cinnamon.desktop.keybindings.wm toggle-shaded @as []
org.cinnamon.desktop.keybindings.wm unmaximize ['<Alt>F5']

```




## 設定方式

> 接著我們在『[設定「主要」的「按鍵綁定」](https://samwhelp.github.io/note-about-linuxmint-cinnamon/read/howto/config-keybind/config-keybind-main.html)』這篇來說明如何修改設定。




## 相關議題

* [設定「主要」的「按鍵綁定」](https://samwhelp.github.io/note-about-linuxmint-cinnamon/read/howto/config-keybind/config-keybind-main.html)
* [設定「自訂」的「按鍵綁定」](https://samwhelp.github.io/note-about-linuxmint-cinnamon/read/howto/config-keybind/config-keybind-custom.html)
* [設定「Alt-Tab Switcher Keybind」](https://samwhelp.github.io/note-about-linuxmint-cinnamon/read/howto/config-alttab-switcher/config-alttab-switcher-keybind.html)
