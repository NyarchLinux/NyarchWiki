# 安装应用程序
在 Nyarch Linux 上，你可以通过多种方式安装应用程序，这些方式被称为“包格式”。
本页面介绍不同包格式之间的区别，以及如何安装和管理它们。

支持的包格式：

1. [Arch Linux 软件包](#arch-linux-软件包)（pacman、.tar.zst）
2. [Flatpak](#flatpak)（应用商店、.flatpakref、.flatpak）
3. [AppImage](#appimage)（.appimage）
4. [Arch 用户仓库](#arch-用户仓库)（yay 和 paru）

## Arch Linux 软件包

（几乎）每个 Linux 发行版都有包管理器：它帮助你在电脑上安装、移除和更新软件包。

在 Arch Linux 上，包管理器是 `pacman`。

由于多种原因，`pacman` 应仅在终端中使用，并且需要管理员权限。

以下是 `pacman` 的一些基本用法。如果你想了解更详细的说明，请查看 [Arch 中文维基 | Pacman](https://wiki.archlinuxcn.org/wiki/Pacman)。

### 如何安装软件包
```bash
sudo pacman -S package
```

例如，要安装 `firefox`，你可以输入
```bash
sudo pacman -S firefox
```

### 如何移除软件包
```bash
sudo pacman -R package
```
如果你还想移除它的依赖项，可以使用 `-Rns`。

### 如何更新所有软件包
```bash
sudo pacman -Syu
```
### 如何搜索软件包
```bash
sudo pacman -Ss package
```

## Flatpak

Flatpak 是一种特殊的包格式，允许你在**沙盒**环境中安装应用程序喵～

这意味着你可以像在智能手机上一样，轻松管理应用程序的权限。

Flatpak 有一些优点和缺点：

- 优点：
  - 可以在 *任何* Linux 发行版上运行
  - 你可以控制应用程序的权限
  - 可以通过应用商店轻松安装
  - 无需管理员权限即可安装应用程序
- 缺点：
  - 比原生软件包占用更多磁盘空间
  - 某些不适合在沙盒中运行的软件有时会出问题
  - 对于终端程序，通常需要额外步骤

### 什么时候应该安装 Flatpak？

- 当软件主要设计为以 Flatpak 形式运行时（例如 Bottles）
- 当你需要安装不受信任的软件时（你可以控制其权限）
- 当它是 GTK/GNOME 应用程序时（因为 Nyarch 自带相应运行时，安装很快）
- 当软件不是终端程序时

### 安装 Flatpak

#### GNOME 软件

你可以使用 **GNOME 软件**来查找、安装、卸载和更新 Flatpak 应用程序。

![图片](https://github.com/user-attachments/assets/34132dbc-f032-475b-90f9-1eec75f1eabd)

![图片](https://github.com/user-attachments/assets/e2da8b38-7de6-44d3-a045-7a1b5fd4291a)

#### 从 Flathub 安装

你可以在 [Flathub](https://flathub.org/) 上找到 Flatpak 应用。从那里安装应用时，浏览器会下载一个 `.flatpakref` 文件；点击该文件后，应用会在 GNOME 软件中打开。

**注意**：Flathub 上的每个应用也都可以在 GNOME 软件中找到。

#### 命令行
```bash
flatpak install application.id
```
例如，通过 Flatpak 安装 firefox
```bash
flatpak install org.mozilla.firefox
```
通过命令行，你还可以安装 `.flatpak` 文件。

要做到这一点，你可以直接运行
```bash
flatpak install file.flatpak
```

此外，双击 `.flatpak` 文件会在 Gnome 软件中打开以安装它。

### 管理 Flatpak 权限

你可以使用 Flatseal 管理 flatpak 权限。

## AppImage

**AppImage** 是一种可在任何 Linux 发行版上运行的特殊格式。

- 优点：
  - 可以在*任何* Linux 发行版上运行
- 缺点：
  - 不会与其他应用共享库
  - 通常运行较慢
  - 通常不支持系统主题

如果还有其他包格式可用，通常不建议使用 AppImage。
**仅在没有其他替代方案时使用** AppImage。

### 安装和管理 AppImage

下载 AppImage 后，双击即可启动 **GearLever**。

GearLever 是一款简单的工具，可帮助你安装和卸载 AppImage。
你可以选择仅运行一次 AppImage 而不安装，也可以将其添加到应用菜单。

#### 从命令行运行 appimages

你也可以直接从命令行运行 appimage：

1. 赋予它执行权限

        chmod +x application.appimage

2. 运行它

        ./application.appimage

## Arch 用户仓库

[AUR](https://aur.archlinux.org/)（Arch 用户仓库）是一个由社区驱动的大型软件包仓库，用于存放 Arch Linux 官方不支持的软件包。**如果某个应用存在，你很可能会在 AUR 中找到它。**

Nyarch Linux 完全兼容 AUR，因为它使用默认的 Arch Linux 仓库。

**警告**：AUR 上的软件包由用户上传，因此可能并不安全。建议始终通过软件包构建检查其是否可信喵～

### 安装软件包

要安装 AUR 软件包，你需要一个 [Arch 中文维基 | AUR 助手](https://wiki.archlinuxcn.org/wiki/AUR_%E5%8A%A9%E6%89%8B)。

默认情况下，Nyarch Linux 将 `yay` 作为默认 AUR 助手（或者 `nyay`，因为 lol nya）。

要安装 AUR 软件包，可以运行：

```bash
yay -S package
```
例如，
```bash
yay -S zen-browser-bin
```

#### 更新软件包
```bash
yay
```
更新 AUR 中的所有软件包

### 使用 paru 进行

`paru` 是一个功能丰富的 AUR 助手，使用 Rust 编写，常被视为 `yay` 的继任者，提供更安全的默认设置和更活跃的维护。

要安装 `paru`，可以运行：

```bash
sudo pacman -S --needed base-devel git
git clone https://aur.archlinux.org/paru.git
cd paru
makepkg -si
```

#### 使用 paru 安装软件包

`paru` 使用与 `pacman` 类似的语法，使其易于上手。

要安装 AUR 软件包，你可以运行：
```bash
paru -S package
```
例如，
```bash
paru -S chrome
```

#### 更新软件包
```bash
paru
```
或
```bash
paru -Syu
```
这会同时更新官方仓库和 AUR 中的所有软件包 。

#### 关于使用 paru 的小提示

- **退出审阅**：审阅过程中按 `q` 即可退出。
- **查看 PKGBUILD**：`paru -Gp package` 可以在安装前查看软件包的构建脚本。
- **查看 AUR 评论**：`paru -Gc package` 可以查看其他用户对该软件包的评论。
- **交互式搜索**：直接运行 `paru searchterm` 可以交互式搜索并选择安装。
- **跳过审阅**：`paru -S package --skipreview`（不推荐用于不受信任的软件包）。

### 软件包名称指南

同一个程序可能对应多个软件包。以下是 Vesktop 的一个示例：

![图片](https://github.com/user-attachments/assets/e38667d5-a46a-4d39-8205-ad3ee276d90b)

可根据后缀判断：

- `-git`：该软件包基于 Git 仓库中的最新代码构建，可能不稳定，但能获得最新功能和更新。此外，它需要**从源代码编译**。
- `-bin`：该软件包是二进制包，已**预编译**，可直接使用，无需从源代码构建。
- 如果没有后缀，通常表示该软件包是“发布”版本，即软件的最新稳定版本。
