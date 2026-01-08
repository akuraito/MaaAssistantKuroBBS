<!-- markdownlint-disable MD033 MD041 -->

<div align="center">

# MaaAssistantKuroBBS

MAKBBS 是指 Maa Assistant KuroBBS

基于 MAA 全新架构的 库街区 小助手

图像技术 + 模拟控制，解放双手！

由 [MaaFramework](https://github.com/MaaXYZ/MaaFramework) 强力驱动！

![Downloads](https://img.shields.io/github/downloads/akuraito/MaaAssistantKuroBBS/total)

</div>

## 即刻开始

> 以 Windows 用户为主，其他系统请照葫芦画瓢。

- 模拟器准备：
  1. 将模拟器分辨率修改为 `1280x720 320dpi` 或 `1920x1080 480dpi`（推荐）（[模拟器支持情况参考](https://docs.maa.plus/zh-cn/manual/device/windows.html)）
  1. 使用移动页面打开[库街区APP下载页](https://www.kurobbs.com/download.html)并下载库街区APP（如模拟器自带的浏览器、或使用 Chrome 浏览器的[模拟移动设备功能](https://developer.chrome.google.cn/docs/devtools/device-mode?hl=zh-cn)）
  1. 在模拟器上安装并登录库街区APP

- MaaAssistantKuroBBS 准备：
  1. 下载对应平台的压缩包：[Releases](https://github.com/akuraito/MaaAssistantKuroBBS/releases/latest)
  1. 将压缩包解压到没有中文的目录下

> 压缩包文件中应包含 `MaaPiCli.exe`（命令行界面）与 `MFAAvalonia.exe`（图形化界面），可以选择其一使用。

### 与 [MAA_Punish](https://github.com/overflow65537/MAA_Punish) 共同使用

1. 在 MAA_Punish 中点击 `完成后运行`
1. 在 `完成后` 中勾选 `运行其他程序`
1. 在 `程序路径` 中填入 `D:/Software/MAKBBS/MaaPiCli.exe` 或 `D:/Software/MAKBBS/MFAAvalonia.exe`。
    - 若选择 `MaaPiCli.exe`，在下方 `程序参数` 中填入 `-d` 可跳过交互直接运行任务
    - 若选择 `MFAAvalonia.exe`，可在 `MFAAvalonia.exe` 的 `设置`-`启动设置`-`启动后操作` 中选择 `仅启动脚本`

> 注意：`D:/Software/MAKBBS` 请替换成你自己的 MaaAssistantKuroBBS 目录

## Q&A

Q：为什么我的库街区APP掉登录？

A：同一账号只能同时登录一个库街区APP，请勿在其他库街区APP中再次登录。

Q：怎么突然用不了？

A：通常是因为每月签到页换颜色、临时的七日签到、连续签到等增加奖励等造成的页面变化，请等待更新。

Q：会支持多个战双账号签到、库街区自身的签到吗？

A：不会。

Q：`MaaPiCli.exe` 可否在结束后打开其他软件？

A：不行，仅 `MFAAvalonia.exe` 可以结束后打开其他软件。

## 开发

**如果你要编译源码才看这节，否则直接 [下载](https://github.com/akuraito/MaaAssistantKuroBBS/releases/latest) 即可**

_欢迎大佬们来带带~_

1. 克隆本项目

    ```bash
    git clone https://github.com/akuraito/MaaAssistantKuroBBS.git
    ```

1. 下载 MaaFramework 的 [Release 包](https://github.com/MaaXYZ/MaaFramework/releases)，解压到 `deps` 文件夹中
1. 下载 OCR（文字识别）资源文件 [ppocr_v5.zip](https://download.maafw.xyz/MaaCommonAssets/OCR/ppocr_v5/ppocr_v5-zh_cn.zip) 解压到 `assets/resource/model/ocr/` 目录下，确保路径如下：

    ```tree
    assets/resource/model/ocr/
    ├── det.onnx
    ├── keys.txt
    └── rec.onnx
    ```

    > 您不需要将 OCR 资源文件上传到您的代码仓库中。`.gitignore` 已经忽略了 `assets/resource/model/ocr/` 目录，且 GitHub workflow 在发布版本时会自动配置这些资源文件。

1. 进行开发工作，按您的业务需求修改 `assets` 中的资源文件，请参考 [MaaFramework 相关文档](https://github.com/MaaXYZ/MaaFramework/blob/main/docs/zh_cn/1.1-快速开始.md#资源准备)。

## 鸣谢

本项目参考了以下仓库

- [MaaAssistantSkland](https://github.com/MaaXYZ/MaaAssistantSkland) ![license](https://img.shields.io/github/license/MaaXYZ/MaaAssistantSkland)  
- [MAA_Punish](https://github.com/overflow65537/MAA_Punish) ![license](https://img.shields.io/github/license/overflow65537/MAA_Punish)

本项目由 **[MaaFramework](https://github.com/MaaXYZ/MaaFramework)** 强力驱动！

> **MaaFramework** 是基于图像识别技术、运用 [MAA](https://github.com/MaaAssistantArknights/MaaAssistantArknights) 开发经验去芜存菁、完全重写的新一代自动化黑盒测试框架。
>
> 低代码的同时仍拥有高扩展性，旨在打造一款丰富、领先、且实用的开源库，助力开发者轻松编写出更好的黑盒测试程序，并推广普及。

感谢以下开发者对本项目作出的贡献：

[![Contributors](https://contrib.rocks/image?repo=akuraito/MaaAssistantKuroBBS&max=1000)](https://github.com/akuraito/MaaAssistantKuroBBS/graphs/contributors)
