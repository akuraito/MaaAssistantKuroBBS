<!-- markdownlint-disable MD033 MD041 -->

<div align="center">

# MaaAssistantKuroBBS

</div>

本项目是利用 [MaaFramework](https://github.com/MaaXYZ/MaaFramework) 所提供的项目模板并参考了 [MaaAssistantSkland](https://github.com/MaaXYZ/MaaAssistantSkland) 而出生的 [库街区](https://www.kurobbs.com) 小助手。

当前仅实现战双每日签到，如需鸣潮每日签到，请使用 [MaaMihoyoBBS](https://github.com/shawn01234/MaaMihoyoBBS)。

## 即刻开始

  > 以 Windows 用户为主，其他系统请照葫芦画瓢。

- 模拟器准备：
  1. 将模拟器分辨率修改为 `1280x720 320dpi` 或 `1920x1080 480dpi`（推荐）（[模拟器支持情况参考](https://maa.plus/docs/zh-cn/manual/device/)）
  1. 使用移动页面打开[库街区APP下载页](https://www.kurobbs.com/download.html)并下载库街区APP（如模拟器自带的浏览器、或使用 Chrome 浏览器的[模拟移动设备功能](https://developer.chrome.google.cn/docs/devtools/device-mode?hl=zh-cn)）
  1. 在模拟器上安装并登录库街区APP
- MaaAssistantKuroBBS 准备：
  1. 下载对应平台的压缩包：[Releases](https://github.com/akuraito/MaaAssistantKuroBBS/releases)
  1. 将压缩包解压到没有中文的目录下

压缩包文件中应包含 `MaaPiCli.exe`（命令行界面）与 `MFAAvalonia.exe`（图形化界面），可以选择其一使用。

- 命令行界面
  1. 首次使用，打开模拟器，双击打开 `MaaPiCli.exe` 或 通过 CMD 执行 `MaaPiCli.exe`
  1. 选择ADB（本教程以 Auto detect 为例）
  1. 等待扫描设备（设备越多等待时间越长）
  1. 选择需要连接的设备
  1. 开始使用吧！

### 与 [MAA_Punish](https://github.com/overflow65537/MAA_Punish) 共同使用

在 MAA_Punish `资源设置`-`自定义启动`-`结束后运行程序` 中，点击按钮并选择 MaaAssistantKuroBBS 目录中的 `MaaPiCli.exe` 或 `MFAAvalonia.exe`。

- 若选择 `MaaPiCli.exe`，在 下方 `运行参数` 中填入 `-d` 可跳过交互直接运行任务
- 若选择 `MFAAvalonia.exe`，可在 `MFAAvalonia.exe` 的 `设置`-`启动设置`-`启动后操作` 中选择 `启动软件并启动脚本`

如需要一天只运行一次：

1. 在 MaaAssistantKuroBBS 目录中新建文本文件，在其中填入以下内容：

    ```bat
    @echo off
    cd D:/Software/MAKBBS
    set "date_file=last_run_date.txt"
    if not exist "%date_file%" (
        MaaPiCli.exe -d
        echo %date% > "%date_file%"
        exit
    )

    set /p last_run_date=<"%date_file%"
    set "last_run_date=%last_run_date: =%"

    set current_date=%date%
    set "current_date=%current_date: =%"

    if %current_date% neq %last_run_date% (
        MaaPiCli.exe -d
        echo %current_date% > "%date_file%"
    )
    exit
    ```

    > 注意：`D:/Software/MaaAssistantKuroBBS` 请替换成你自己的 MaaAssistantKuroBBS 目录；`MaaPiCli.exe` 可替换为 `MFAAvalonia.exe`

1. 将文本文件重命名为 `finish.bat`

    > 如果重命名后没有弹出修改扩展名的二次确认对话框，且文件图标没有变化，请自行搜索“Windows如何显示文件扩展名”

1. 在 MAA_Punish `资源设置`-`自定义启动`-`结束后运行程序` 中，点击按钮并选择 MaaAssistantKuroBBS 目录中的 `finish.bat`

## Q&A

Q：为什么我的库街区APP掉登录？

A：同一账号只能同时登录一个库街区APP，请勿在其他库街区APP中再次登录。

Q：怎么突然用不了？

A：通常是因为~~每月签到页换颜色~~、临时的七日签到增加奖励等造成的页面变化，请等待更新。

Q：会支持多个战双账号签到、库街区自身的签到吗？

A：不会。

Q：`MaaPiCli.exe` 可否在结束后打开其他软件？

A：不行，仅 `MFAAvalonia.exe` 可以结束后打开其他软件。

## 开发

**如果你要编译源码才看这节，否则直接 [下载](https://github.com/akuraito/MaaAssistantKuroBBS/releases) 即可**

_欢迎大佬们来带带~_

1. 完整克隆本项目及子项目

    ```bash
    git clone --recursive https://github.com/akuraito/MaaAssistantKuroBBS.git
    ```

1. 下载 MaaFramework 的 [Release 包](https://github.com/MaaXYZ/MaaFramework/releases)，解压到 `deps` 文件夹中
1. 安装

    ```bash
    python install.py
    ```

    安装的二进制及相关资源文件在 `install` 目录下

## 开发相关

- `deps/tools/ImageCropper` 可以用来裁剪图片和获取 ROI
- Pipeline 协议请参考 [MaaFramework 的文档](https://github.com/MaaXYZ/MaaFramework/blob/main/docs/zh_cn/3.1-%E4%BB%BB%E5%8A%A1%E6%B5%81%E6%B0%B4%E7%BA%BF%E5%8D%8F%E8%AE%AE.md)

## 鸣谢

本项目由 **[MaaFramework](https://github.com/MaaXYZ/MaaFramework)** 强力驱动！

  > **MaaFramework** 是基于图像识别技术、运用 [MAA](https://github.com/MaaAssistantArknights/MaaAssistantArknights) 开发经验去芜存菁、完全重写的新一代自动化黑盒测试框架。
  >
  > 低代码的同时仍拥有高扩展性，旨在打造一款丰富、领先、且实用的开源库，助力开发者轻松编写出更好的黑盒测试程序，并推广普及。

感谢以下开发者对本项目作出的贡献：

[![Contributors](https://contrib.rocks/image?repo=akuraito/MaaAssistantKuroBBS&max=1000)](https://github.com/akuraito/MaaAssistantKuroBBS/graphs/contributors)
