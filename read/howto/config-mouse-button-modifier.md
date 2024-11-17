---
title: 設定「Mouse Button Modifier」
nav_order: 7021
has_children: false
parent: 如何
---


# 設定「Mouse Button Modifier」




## 主題

* [期望功能](#期望功能)
* [設定檔](#設定檔)




## 期望功能

> 我個人習慣「在視窗操作下面兩個動作」，

| 滑鼠按鍵組合                |  功能                   |
| --------------------------- | ----------------------- |
| `Win + [滑鼠左鍵按住拖曳]`  | 視窗移動                |
| `Win + [滑鼠右鍵按住拖曳]`  | 視窗更改大小            |

> 不過在「GXDE」被設定停用了，可以參考下面幾個專案的原始碼。

| 原始碼 |
| ----- |
| linuxdeepin/deepin-kwin/configures/[deepin-kwinrc](https://github.com/linuxdeepin/deepin-kwin/blob/master/configures/deepin-kwinrc#L102-L108) |
| GXDE-OS/deepin-kwin/configures/[deepin-kwinrc](https://github.com/GXDE-OS/deepin-kwin/blob/5.24/configures/deepin-kwinrc#L96-L102) |
| GXDE-OS/gxde-kwin/configures/[kwinrc](https://github.com/GXDE-OS/gxde-kwin/blob/old/configures/kwinrc#L93-L99) |
| GXDE-OS/deepin-kwin/configures/[kwinrc](https://github.com/GXDE-OS/dde-kwin/blob/debian12/configures/kwinrc#L94-L100) |


``` ini
[MouseBindings]
#禁用Alt+鼠标左键移动窗口
CommandAll1=Nothing
#禁用Alt+鼠标中键改变窗口层叠顺序的功能
CommandAll2=Nothing
#禁用Alt+鼠标右键绑定的改变窗口大小的功能
CommandAll3=Nothing
```




## 設定檔

| 設定檔路徑 |
| --- |
| [~/.config/deepin-kwinrc](https://github.com/samwhelp/gxde-adjustment/blob/main/prototype/main/gxde-config/locale/en_us/Main/asset/overlay/etc/skel/.config/deepin-kwinrc#L50-L54) |

> 所以為了恢復我慣用的「Mousebind」，修改「`~/.config/deepin-kwinrc`」設定片段如下

``` ini
[MouseBindings]
CommandAll1=Move
CommandAll2=Toggle raise and lower
CommandAll3=Resize
CommandAllKey=Meta
```


> 一些預設的動作，可以參考原始碼

| 原始碼 |
| ----- |
| GitHub / KDE / kwin / src / [kwin.kcfg](https://github.com/KDE/kwin/blob/master/src/kwin.kcfg#L48-L56) |
| invent.kde.org / kwin / src / [kwin.kcfg](https://invent.kde.org/plasma/kwin/-/blob/master/src/kwin.kcfg?ref_type=heads#L48-L56)


``` xml
        <entry name="CommandAll1" type="String">
            <default>Move</default>
        </entry>
        <entry name="CommandAll2" type="String">
            <default>Toggle raise and lower</default>
        </entry>
        <entry name="CommandAll3" type="String">
            <default>Resize</default>
        </entry>
```
