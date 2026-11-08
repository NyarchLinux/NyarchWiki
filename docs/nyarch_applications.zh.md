# Nyarch 应用程序

本文列出了 Nyarch 应用程序的清单。部分应用程序仅适用于某些 Nyarch 版本。

## Nyarch 导览

Nyarch Tour 在 Nyarch 的首次安装成功后自动启动喵～它的任务是引导猫猫了解 Nyarch 的功能以及如何使用其桌面喵～。

### GNOME 版本

- **应用 ID**：`moe.nyarchlinux.tour`
- **启动命令**：`nyarchtour`（以 Flatpak 安装时则为 `flatpak run moe.nyarchlinux.tour`）
- **GitHub 仓库**：[https://github.com/NyarchLinux/NyarchTour](https://github.com/NyarchLinux/NyarchTour)
- **语言**：`Python`
- **工具包**：`GTK4 + Adwaita`

### KDE 版本

- **应用 ID**：`moe.nyarchlinux.tourqt`
- **启动命令**：`nyarchtourqt`
- **GitHub 仓库**：[https://github.com/NyarchLinux/NyarchTourQT](https://github.com/NyarchLinux/NyarchTourQT)
- **语言**：`Python`
- **工具包**：`QT + Kirigami (PySide6)`

## Catgirl Downloader

Catgirl Downloader 可以从多个来源下载随机猫娘图片喵～

功能：

- 自动重载
- 喵～
- 支持多个猫娘图片来源

支持以下下载源喵～：

- [nekos.moe](https://nekos.moe)
- [waifu.im](https://waifu.im)
- [danbooru](https://danbooru.donmai.us)

### GNOME 版本

- **应用 ID**：`moe.nyarchlinux.catgirldownloader`
- **启动命令**：`catgirldownloader`（以 Flatpak 安装时则为 `flatpak run moe.nyarchlinux.catgirldownloader`）
- **GitHub 仓库**：[https://github.com/NyarchLinux/CatgirlDownloader](https://github.com/NyarchLinux/CatgirlDownloader)
- **语言**：`Python`
- **工具包**：`GTK4 + Adwaita`

### KDE 版本

- **应用 ID**：`moe.nyarchlinux.catgirldownloaderqt`
- **启动命令**：`catgirldownloaderqt`
- **GitHub 仓库**：[https://github.com/NyarchLinux/CatgirlDownloaderQT](https://github.com/NyarchLinux/CatgirlDownloaderQT)
- **语言**：`Python`
- **工具包**：`QT + Kirigami (PySide6)`

## NekoPlay

NekoPlay 是专为看番打造的高性能视频播放器，基于 [Cine](https://github.com/diegopvlk/Cine) 二次开发喵～。它使用 MPV 作为播放内核，在保持简洁界面的同时加入了一批专门针对动画的功能。

功能：

- **简洁界面**：克制、无干扰的设计
- **基于 MPV**：播放性能和格式支持都很强
- **音轨与字幕**：自由切换并同步音轨和字幕
- **画面调节**：亮度、对比度、缩放、宽高比等
- **4K 动画超分**：用 Anime4K 把 720p 的动画放大到 4K 观看喵～
- **90 秒跳过**：一键跳过片头（*大多数* 动画的片头正好是 90 秒）

NekoPlay 的 GNOME 与 KDE 版本共用同一个 GTK 应用，没有单独的 Qt 版本喵～。

### 应用信息

- **应用 ID**：`moe.nyarchlinux.nekoplay`
- **启动命令**：`nekoplay`（以 Flatpak 安装时则为 `flatpak run moe.nyarchlinux.nekoplay`）
- **GitHub 仓库**：[https://github.com/NyarchLinux/NekoPlay](https://github.com/NyarchLinux/NekoPlay)
- **语言**：`Python`
- **工具包**：`GTK4 + Adwaita`

## Nyarch Assistant

Nyarch Assistant 是 Nyarch Linux 官方的 **AI 猫娘**，支持 Live2D / LivePNG 形象、TTS 语音、终端命令执行、扩展以及本地模型喵～。它是 [Newelle](https://github.com/qwersyk/Newelle) 的分支；完整的配置和使用说明见 [Nyarch Assistant](nyarchassistant.md) 页面。

Nyarch Assistant 的 GNOME 与 KDE 版本同样共用同一个 GTK 应用，没有单独的 Qt 版本喵～。

### 应用信息

- **应用 ID**：`moe.nyarchlinux.assistant`
- **启动命令**：`nyarchassistant`（以 Flatpak 安装时则为 `flatpak run moe.nyarchlinux.assistant`）
- **GitHub 仓库**：[https://github.com/NyarchLinux/NyarchAssistant](https://github.com/NyarchLinux/NyarchAssistant)
- **语言**：`Python`
- **工具包**：`GTK4 + Adwaita`
