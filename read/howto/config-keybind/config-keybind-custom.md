---
title: 設定「自訂」的「按鍵綁定」
nav_order: 7020
has_children: false
parent: 設定「按鍵綁定 (Keybind)」
grand_parent: 如何
---


# 設定「自訂」的「按鍵綁定」




## 主題

* [前提](#前提)
* [設定範例](#設定範例)
* [範例腳本](#範例腳本)
* [相關案例](#相關案例)




## 前提




## 設定範例

``` sh

##
## ## Clear Old
##

dconf reset -f /org/cinnamon/desktop/keybindings/custom-keybindings/




##
## ## Keybind Item
##


## ### Logout
dconf write /org/cinnamon/desktop/keybindings/custom-keybindings/system-logout/name "'System_Logout'"
dconf write /org/cinnamon/desktop/keybindings/custom-keybindings/system-logout/command "'cinnamon-session-quit --logout'"
dconf write /org/cinnamon/desktop/keybindings/custom-keybindings/system-logout/binding "['<Shift><Alt>x']"


## ### Shutdown
dconf write /org/cinnamon/desktop/keybindings/custom-keybindings/system-shutdown/name "'System_Shutdown'"
dconf write /org/cinnamon/desktop/keybindings/custom-keybindings/system-shutdown/command "'cinnamon-session-quit --power-off'"
dconf write /org/cinnamon/desktop/keybindings/custom-keybindings/system-shutdown/binding "['<Shift><Alt>z']"


## ### System Settings
dconf write /org/cinnamon/desktop/keybindings/custom-keybindings/system-settings/name "'System_Settings'"
dconf write /org/cinnamon/desktop/keybindings/custom-keybindings/system-settings/command "'cinnamon-settings'"
dconf write /org/cinnamon/desktop/keybindings/custom-keybindings/system-settings/binding "['<Shift><Alt>s']"


## ### Terminal
dconf write /org/cinnamon/desktop/keybindings/custom-keybindings/terminal/name "'Terminal'"
dconf write /org/cinnamon/desktop/keybindings/custom-keybindings/terminal/command "'gnome-terminal'"
dconf write /org/cinnamon/desktop/keybindings/custom-keybindings/terminal/binding "['<Alt>Return']"


## ### File Manager
dconf write /org/cinnamon/desktop/keybindings/custom-keybindings/file-manager/name "'File_Manager'"
dconf write /org/cinnamon/desktop/keybindings/custom-keybindings/file-manager/command "'nemo'"
dconf write /org/cinnamon/desktop/keybindings/custom-keybindings/file-manager/binding "['<Shift><Alt>f']"


## ### Text Editor
dconf write /org/cinnamon/desktop/keybindings/custom-keybindings/text-editor/name "'Text_Editor'"
dconf write /org/cinnamon/desktop/keybindings/custom-keybindings/text-editor/command "'xed'"
dconf write /org/cinnamon/desktop/keybindings/custom-keybindings/text-editor/binding "['<Shift><Alt>e']"


## ### Web Browser
dconf write /org/cinnamon/desktop/keybindings/custom-keybindings/web-browser/name "'Web_Browser'"
dconf write /org/cinnamon/desktop/keybindings/custom-keybindings/web-browser/command "'firefox --new-tab about:blank'"
dconf write /org/cinnamon/desktop/keybindings/custom-keybindings/web-browser/binding "['<Shift><Alt>b']"




##
## ## Custom Keybindings
##

gsettings set org.cinnamon.desktop.keybindings custom-list "['__dummy__', 'system-logout', 'system-shutdown', 'system-settings', 'terminal', 'file-manager', 'text-editor', 'web-browser']"


```

上面設定完後，可以執行下面指令，觀看目前的設定值

``` sh

dconf dump /org/cinnamon/desktop/keybindings/custom-keybindings/

echo

gsettings get org.cinnamon.desktop.keybindings custom-list

```




## 範例腳本

* [範例腳本](https://github.com/samwhelp/note-about-linuxmint-cinnamon/tree/gh-pages/_demo/scripts/keybind)




## 相關案例

* [cinnamon-keybind-custom](https://github.com/samwhelp/note-about-ubuntu/blob/gh-pages/_demo/adjustment/de/cinnamon/part/cinnamon-keybind-custom/config-install.sh)
* [/etc/dconf/db/distro.d/50_cinnamon-keybind-custom.conf](https://github.com/samwhelp/lika-live-build-respin-cinnamon/blob/main/asset/overlay/etc/dconf/db/distro.d/50_cinnamon-keybind-custom.conf)
