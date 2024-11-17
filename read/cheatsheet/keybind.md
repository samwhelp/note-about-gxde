---
title: 鍵盤按鍵綁定一覽表
nav_order: 9010
has_children: false
parent: 一覽表
---


# 鍵盤按鍵綁定一覽表

> 概覽 / [工作流程](https://samwhelp.github.io/note-about-gxde/read/guide/workflow)

> [鍵盤按鍵綁定說明](https://samwhelp.github.io/note-about-gxde/read/config/keybind.html)




## 主題

* [設定檔](#設定檔)
* [系統操作](#系統操作)
* [開啟應用程式](#開啟應用程式)
* [視窗操作](#視窗操作)
* [工作空間](#工作空間)
* [相關連結](#相關連結)




## 設定檔

> 關於「按鍵綁定」的設定檔，有兩個如下

| 設定檔 |
| ----- |
| [~/.config/kglobalshortcutsrc](https://github.com/samwhelp/gxde-adjustment/blob/main/prototype/main/gxde-config/locale/en_us/Deepin-Dark/asset/overlay/etc/skel/.config/kglobalshortcutsrc#L45-L212) |
| [~/.config/deepin/dde-daemon/keybinding/custom.ini](https://github.com/samwhelp/gxde-adjustment/blob/main/prototype/main/gxde-config/locale/en_us/Deepin-Dark/asset/overlay/etc/skel/.config/deepin/dde-daemon/keybinding/custom.ini) |

> 有一部份則是要透過「gsettings」或「donf」來設定。

> 可以執行「`gsettings list-recursively | grep keybind`」來找到。

> 也可以執行「`gsettings list-recursively | grep com.deepin.dde.keybinding.system`」來找到。

> 也可以透過撰寫「`/usr/share/glib-2.0/schemas/*.gschema.override`」來設定「預設值」，然後要執行「`sudo glib-compile-schemas /usr/share/glib-2.0/schemas`」讓它生效。

> 這部份可以參考下面的實作案例

| 實作案例 |
| ------- |
| gxde-iso-builder-refactoring/[asset/overlay/usr/share/glib-2.0/schemas/95_gxde-adjustment-keybind.gschema.override](https://github.com/samwhelp/gxde-iso-builder-refactoring/blob/main/asset/overlay/usr/share/glib-2.0/schemas/95_gxde-adjustment-keybind.gschema.override) |
| gxde-iso-builder-refactoring/[factory/hook/1110-update-glib-schemas.hook.chroot](https://github.com/samwhelp/gxde-iso-builder-refactoring/blob/main/factory/hook/1110-update-glib-schemas.hook.chroot#L23) |




## 系統操作

| 按鍵組合           | 功能                                    | 執行指令                   |
| ------------------ | --------------------------------------- | -------------------------- |
| `Alt + Shift + z`  | 顯示「離開系統選單」                    | `dde-shutdown`             |
| `Alt + Shift + x`  | 顯示「離開系統選單」                    | `dde-shutdown`             |
| `Alt + Shift + l`  | 鎖住螢幕                                | `dde-lock`                 |
| `Win + d`          | 切換「顯示桌面」                        | `Show Desktop=`            |
| `Win + grave`      | 顯示「工作空間選單」                    | `ShowDesktopGrid=`         |
| `Win + Tab`        | 切換「顯示目前工作空間的所有視窗預覽」  | `Expose=`                  |
| `Win + c`          | 顯示「所有開啟視窗預覽」                | `ExposeAll=`               |
| `Alt + F1`         | 顯示「應用程式啟動選單」                |                            |
| `Alt + F3`         | 顯示「視窗操作選單」                    | `Window Operations Menu=`  |
| `Alt + Space`      | 顯示「視窗操作選單」                    | `Window Operations Menu=`  |





## 開啟應用程式

> 可以按下「`Alt + F1`」執行「`gxde-launcher`」，就可以找到其他的「應用程式」來執行




## 開啟應用程式 / Terminal

| 按鍵組合           | 功能           | 執行指令           |
| ------------------ | -------------- | ------------------ |
| `Alt + Enter`      | 開啟 Terminal  | `gxde-terminal`    |
| `Alt + Shift + a`  | 開啟 Terminal  | `gxde-terminal`    |
| `Alt + Ctrl + a`   | 開啟 Terminal  | `sakura`           |
| `Alt + Shift + t`  | 開啟 Terminal  | `xfce4-terminal`   |
| `Alt + Ctrl + t`   | 開啟 Terminal  | `qterminal`        |




## 開啟應用程式 / 常用的應用程式

| 按鍵組合           | 功能            | 執行指令                         |
| ------------------ | --------------- | -------------------------------- |
| `Alt + Shift + f`  | 開啟檔案管理器  | `dde-file-manager`               |
| `Alt + Shift + g`  | 開啟檔案管理器  | `pcmanfm-qt`                     |
| `Alt + Shift + e`  | 開啟文字編輯器  | `gxde-editor`                    |
| `Alt + Shift + b`  | 開啟網頁瀏覽器  | `firefox --new-tab about:blank`  |
| `Alt + Shift + s`  | 開啟系統設定    | `dde-control-center -t`          |




## 視窗操作

| 按鍵組合   | 功能                               | 執行指令                       |
| ---------- | ---------------------------------- | ------------------------------ |
| `Win + q`  | 關閉視窗                           | `Window Close=`                |
| `Win + f`  | 視窗全螢幕                         | `Window Fullscreen=`           |
| `F11`      | 視窗全螢幕                         | `Window Fullscreen=`           |
| `Win + w`  | 視窗最大化                         | `Window Maximize=`             |
| `Win + x`  | 視窗最小化                         | `Window Minimize=`             |
| `Win + e`  | 開始「視窗移動」                   | `Window Move=`                 |
| `Win + r`  | 開始「視窗更改大小」               | `Window Resize=`               |
| `Win + t`  | 視窗保持永遠在最上方               | `Window Above Other Windows=`  |
| `Win + b`  | 視窗保持永遠在最下方               | `Window Below Other Windows=`  |
| `Win + y`  | 視窗內容區塊收合                   | `Window Shade=`                |
| `Win + n`  | 切換顯示隱藏視窗裝飾(Decorations)  | `Window No Border=`            |
| `Win + z`  | 將下方視窗移上來                   | `Toggle Window Raise/Lower=`   |
| `Win + m`  | 視窗移動至畫面中央部位             | `Window Move Center`           |
| `Win + ;`  | 視窗更加透明                       | `Decrease Opacity=`            |
| `Win + '`  | 視窗更不透明                       | `Increase Opacity=`            |




## 視窗操作 / 視窗聚焦切換

| 按鍵組合     | 功能                    | 執行指令                                       |
| ------------ | ----------------------- | ---------------------------------------------- |
| `Win + a`    | 聚焦切換到前面一個視窗  | `Walk Through Windows (Reverse)=`              |
| `Win + s`    | 聚焦切換到後面一個視窗  | `Walk Through Windows=`                        |
| `Win + Esc`  | 聚焦切換到前面一個視窗  | `Walk Through Windows Alternative=`            |
| `Alt + Esc`  | 聚焦切換到後面一個視窗  | `Walk Through Windows Alternative (Reverse)=`  |




## 視窗操作 / 視窗平鋪移動

| 按鍵組合       | 功能                                  | 執行指令                     |
| -------------- | ------------------------------------- | ---------------------------- |
| `Win + Up`     | 視窗更改大小，移動至北方(畫面上半部)  | `Window Quick Tile Top=`     |
| `Win + Down`   | 視窗更改大小，移動至南方(畫面下半部)  | `Window Quick Tile Bottom=`  |
| `Win + Left`   | 視窗更改大小，移動至西方(畫面左半部)  | `Window Quick Tile Left=`    |
| `Win + Right`  | 視窗更改大小，移動至東方(畫面右半部)  | `Window Quick Tile Right=`   |




## 工作空間

> 我個人定義的工作空間

| 工作空間 | 名稱  |
| -------- | ----- |
| 1        | File  |
| 2        | Edit  |
| 3        | Web   |
| 4        | Term  |
| 5        | Misc  |

> 目前只有開啟「四個」工作空間



## 工作空間 / 循環切換

| 按鍵組合   | 功能                  | 執行指令                            |
| ---------- | --------------------- | ----------------------------------- |
| `Alt + a`  | 切換到上一個工作空間  | `Switch One Desktop to the Left=`   |
| `Alt + s`  | 切換到下一個工作空間  | `Switch One Desktop to the Right=`  |




## 工作空間 / 指定切換

| 按鍵組合          | 功能                     | 執行指令                |
| ----------------- | ------------------------ | ----------------------- |
| `Alt + Ctrl + 1`  | 切換到工作空間 1 (File)  | `Switch to Desktop 1=`  |
| `Alt + Ctrl + 2`  | 切換到工作空間 2 (Edit)  | `Switch to Desktop 2=`  |
| `Alt + Ctrl + 3`  | 切換到工作空間 3 (Web)   | `Switch to Desktop 3=`  |
| `Alt + Ctrl + 4`  | 切換到工作空間 4 (Term)  | `Switch to Desktop 4=`  |
| `Alt + Ctrl + 5`  | 切換到工作空間 5 (Misc)  | `Switch to Desktop 5=`  |
| `Alt + Ctrl + 6`  | 切換到工作空間 6         | `Switch to Desktop 6=`  |
| `Alt + Ctrl + 7`  | 切換到工作空間 7         | `Switch to Desktop 7=`  |
| `Alt + Ctrl + 8`  | 切換到工作空間 8         | `Switch to Desktop 8=`  |
| `Alt + Ctrl + 9`  | 切換到工作空間 9         | `Switch to Desktop 9=`  |




## 工作空間 / 視窗移到工作空間

| 按鍵組合           | 功能                               | 執行指令                |
| -----------------  | ---------------------------------- | ----------------------- |
| `Alt + Shift + 1`  | 「視窗」移到「工作空間 1 (File)」  | `Window to Desktop 1=`  |
| `Alt + Shift + 2`  | 「視窗」移到「工作空間 2 (Edit)」  | `Window to Desktop 2=`  |
| `Alt + Shift + 3`  | 「視窗」移到「工作空間 3 (Web) 」  | `Window to Desktop 3=`  |
| `Alt + Shift + 4`  | 「視窗」移到「工作空間 4 (Term)」  | `Window to Desktop 4=`  |
| `Alt + Shift + 5`  | 「視窗」移到「工作空間 5 (Misc)」  | `Window to Desktop 5=`  |
| `Alt + Shift + 6`  | 「視窗」移到「工作空間 6」         | `Window to Desktop 6=`  |
| `Alt + Shift + 7`  | 「視窗」移到「工作空間 7」         | `Window to Desktop 7=`  |
| `Alt + Shift + 8`  | 「視窗」移到「工作空間 8」         | `Window to Desktop 8=`  |
| `Alt + Shift + 9`  | 「視窗」移到「工作空間 9」         | `Window to Desktop 9=`  |




## 工作空間 / 桌面放大或縮小

| 按鍵組合   | 功能              | 執行指令             |
| ---------- | ----------------- | -------------------- |
| `Win + 0`  | 桌面恢復原來大小  | `view_actual_size=`  |
| `Win + -`  | 桌面縮小          | `view_zoom_out=`     |
| `Win + =`  | 桌面放大          | `view_zoom_in=`      |




## 相關連結

| 相關連結 |
| ------- |
| [鍵盤按鍵綁定](https://samwhelp.github.io/note-about-gxde/read/config/keybind.html) |
| Lingmo OS 探索筆記 / [鍵盤按鍵綁定一覽表](https://samwhelp.github.io/note-about-lingmo/read/cheatsheet/keybind.html) |
