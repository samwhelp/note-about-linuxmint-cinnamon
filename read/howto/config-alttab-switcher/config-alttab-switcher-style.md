---
title: 設定「Alt-Tab Switcher Style」
nav_order: 7010
has_children: false
parent: 設定「Alt-Tab Switcher」
grand_parent: 如何
---


# 設定「Alt-Tab Switcher Style」




## 主題

* [前提](#前提)
* [設定方式](#設定方式)




## 前提

在大部份的「桌面環境」，透過知名的綁定「`Alt + Tab`」，可以用來「切換聚焦視窗」。

在「Cinnamon Desktop」有提供設定，可以設定「切換時的視覺效果」。

可以執行下面指令，找到該設定。

``` sh
gsettings list-recursively | grep alttab
```


顯示類似如下

```
org.cinnamon alttab-minimized-aware true
org.cinnamon alttab-switcher-delay 100
org.cinnamon alttab-switcher-enforce-primary-monitor false
org.cinnamon alttab-switcher-show-all-workspaces false
org.cinnamon alttab-switcher-style 'icons+thumbnails'
org.cinnamon alttab-switcher-warp-mouse-pointer false
```

> 該設定是「`org.cinnamon alttab-switcher-style 'icons+thumbnails'`」這一行。


執行

``` sh
grep 'alttab-switcher-style' /usr/share/glib-2.0/schemas/*
```

顯示

``` xml
/usr/share/glib-2.0/schemas/org.cinnamon.gschema.xml:    <key name="alttab-switcher-style" type="s">
```



執行

``` sh
grep 'alttab-switcher-style' /usr/share/glib-2.0/schemas/org.cinnamon.gschema.xml -A 7
```

顯示

``` xml
    <key name="alttab-switcher-style" type="s">
      <default>"icons+thumbnails"</default>
      <summary>ALT-tab switcher style</summary>
      <description>
       Controls the style of the ALT-tab window switcher. Can be any combination of "icons", "preview" and "thumbnails", separated by "+".
      </description>
    </key>

```



## 設定方式

## 圖形介面操作

執行

``` sh
grep '^Exec=' /usr/share/applications/cinnamon-settings-windows.desktop
```

顯示

``` sh
Exec=cinnamon-settings windows
```

執行

``` sh
grep 'windows' /usr/share/cinnamon/cinnamon-settings/cinnamon-settings.py
```

顯示

``` python
    "windows":          {"titlebar": 0, "behavior": 1, "alttab": 2},
    'window':           'windows',
```

執行

``` sh
grep 'alttab_styles =' /usr/share/cinnamon/cinnamon-settings/modules/cs_windows.py -A 8
```

顯示

``` python
            alttab_styles = [
                ["icons", _("Icons only")],
                ["thumbnails", _("Thumbnails only")],
                ["icons+thumbnails", _("Icons and thumbnails")],
                ["icons+preview", _("Icons and window preview")],
                ["preview", _("Window preview (no icons)")],
                ["coverflow", _("Coverflow (3D)")],
                ["timeline", _("Timeline (3D)")]
            ]
```


> 執行下面指令，就會跳出設定視窗，直接切換到「System Settings / Windows / Alt-Tab」這個頁面。

``` sh
cinnamon-settings windows -t alttab
```

可以看到一個設定項目「`Alt-Tab Switcher Style`」，有「下拉選單」可以選取，其中的「選項列表」如下

| 選項                      　 | 設定值              | 指令設定範例                      |
| ---------------------------- | ------------------- | --------------------------------- |
| `Icons only` 　　　          | `icons`             | [指令設定範例](#icons)            |
| `Thumbnails only`            | `thumbnails`        | [指令設定範例](#thumbnails)       |
| `Icons and thumbnails`       | `icons+thumbnails`  | [指令設定範例](#iconsthumbnails)  |
| `Icons and window preview`   | `icons+preview"`    | [指令設定範例](#iconspreview)     |
| `Window preview (no icons)`  | `preview`           | [指令設定範例](#preview)          |
| `Coverflow (3D)`             | `coverflow`         | [指令設定範例](#coverflow)        |
| `Timeline (3D)`              | `timeline`          | [指令設定範例](#timeline)         |


> 只要從「下拉選單」選擇你想呈現「切換時的視覺效果」就可以設定成功了。




## 指令操作

> 根據上面的「選項列表」，就可以透過指令操作，參考下面範例




### icons

> 執行下面指令，設定成「`Icons only`」。

``` sh
gsettings set org.cinnamon alttab-switcher-style 'icons'
```

執行下面指令，觀看目前「設定值」。

``` sh
gsettings get org.cinnamon alttab-switcher-style
```

顯示

```
'icons'
```

若要恢復成「預設值」，則是執行下面指令。

``` sh
gsettings reset org.cinnamon alttab-switcher-style
```




### thumbnails

> 執行下面指令，設定成「`Thumbnails only`」。

``` sh
gsettings set org.cinnamon alttab-switcher-style 'thumbnails'
```




### icons+thumbnails

> 執行下面指令，設定成「`Icons and thumbnails`」。

``` sh
gsettings set org.cinnamon alttab-switcher-style 'icons+thumbnails'
```




### icons+preview

> 執行下面指令，設定成「`Icons and window preview`」。

``` sh
gsettings set org.cinnamon alttab-switcher-style 'icons+preview'
```




### preview

> 執行下面指令，設定成「`Window preview (no icons)`」。

``` sh
gsettings set org.cinnamon alttab-switcher-style 'preview'
```




### coverflow

> 執行下面指令，設定成「`Coverflow (3D)`」。

``` sh
gsettings set org.cinnamon alttab-switcher-style 'coverflow'
```




### timeline

> 執行下面指令，設定成「`Timeline (3D)`」。

``` sh
gsettings set org.cinnamon alttab-switcher-style 'timeline'
```




## 額外探索紀錄

> 以下只是探索過程中，執行過的指令，和顯示結果，紀錄下來提供參考和備忘。


> 執行下面指令

``` sh
dpkg -S /usr/share/applications/cinnamon-settings-windows.desktop
```

顯示

```
cinnamon: /usr/share/applications/cinnamon-settings-windows.desktop
```


> 執行下面指令

``` sh
dpkg -S /usr/share/cinnamon/cinnamon-settings/cinnamon-settings.py
```

顯示

```
cinnamon-common: /usr/share/cinnamon/cinnamon-settings/cinnamon-settings.py
```



> 執行下面指令

``` sh
dpkg -L cinnamon-common | grep modules
```

顯示

```
/usr/share/cinnamon/cinnamon-settings/modules
/usr/share/cinnamon/cinnamon-settings/modules/cs_accessibility.py
/usr/share/cinnamon/cinnamon-settings/modules/cs_actions.py
/usr/share/cinnamon/cinnamon-settings/modules/cs_applets.py
/usr/share/cinnamon/cinnamon-settings/modules/cs_backgrounds.py
/usr/share/cinnamon/cinnamon-settings/modules/cs_calendar.py
/usr/share/cinnamon/cinnamon-settings/modules/cs_default.py
/usr/share/cinnamon/cinnamon-settings/modules/cs_desklets.py
/usr/share/cinnamon/cinnamon-settings/modules/cs_desktop.py
/usr/share/cinnamon/cinnamon-settings/modules/cs_display.py
/usr/share/cinnamon/cinnamon-settings/modules/cs_effects.py
/usr/share/cinnamon/cinnamon-settings/modules/cs_extensions.py
/usr/share/cinnamon/cinnamon-settings/modules/cs_fonts.py
/usr/share/cinnamon/cinnamon-settings/modules/cs_general.py
/usr/share/cinnamon/cinnamon-settings/modules/cs_gestures.py
/usr/share/cinnamon/cinnamon-settings/modules/cs_hotcorner.py
/usr/share/cinnamon/cinnamon-settings/modules/cs_info.py
/usr/share/cinnamon/cinnamon-settings/modules/cs_keyboard.py
/usr/share/cinnamon/cinnamon-settings/modules/cs_mouse.py
/usr/share/cinnamon/cinnamon-settings/modules/cs_nightlight.py
/usr/share/cinnamon/cinnamon-settings/modules/cs_notifications.py
/usr/share/cinnamon/cinnamon-settings/modules/cs_panel.py
/usr/share/cinnamon/cinnamon-settings/modules/cs_power.py
/usr/share/cinnamon/cinnamon-settings/modules/cs_privacy.py
/usr/share/cinnamon/cinnamon-settings/modules/cs_screensaver.py
/usr/share/cinnamon/cinnamon-settings/modules/cs_sound.py
/usr/share/cinnamon/cinnamon-settings/modules/cs_startup.py
/usr/share/cinnamon/cinnamon-settings/modules/cs_themes.py
/usr/share/cinnamon/cinnamon-settings/modules/cs_tiling.py
/usr/share/cinnamon/cinnamon-settings/modules/cs_user.py
/usr/share/cinnamon/cinnamon-settings/modules/cs_windows.py
/usr/share/cinnamon/cinnamon-settings/modules/cs_workspaces.py
```
