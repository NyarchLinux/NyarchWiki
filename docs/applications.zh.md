# 安装应用程序
在 Nyarch Linux 上，你可以通过多种方式安装应用程序，这些方式被称为"包格式"。
本页面解释了不同包格式之间的区别以及如何安装和管理它们。

支持的包格式：

1. [Arch Linux 包](#arch-linux-packages) (pacman, .tar.zst)
2. [Flatpaks](#flatpaks) (商店, .flatpakref, .flatpak)
3. [AppImages](#appimages) (.appimage)
4. [Arch 用户仓库](#arch-user-repository) (yay & paru)

## Arch Linux Packages  
（几乎）每个 Linux 发行版都有一个包管理器：它帮助你在电脑上安装、移除和更新软件包。

在 Arch Linux 上，包管理器是 `pacman`。

由于多种原因，pacman 应该只在终端中使用，并且需要管理员权限。

以下是 `pacman` 的一些基本用法，如果你想了解更详细的说明，请查看 [Arch Wiki 上的 pacman](https://wiki.archlinux.org/title/Pacman )

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

## Flatpaks
Flatpak 是一种特殊的包格式，允许你在**沙盒**环境中安装应用程序喵～。

这意味着你可以像智能手机一样轻松管理应用程序的权限。

Flatpaks 有一些优点和缺点：
- 优点：
    - 它们可以在*任何* Linux 发行版上运行
    - 你可以控制它们的权限
    - 通过商店轻松安装
    - 你可以在没有管理员权限的情况下安装应用程序
- 缺点：
    - 它们比原生包占用更多磁盘空间
    - 某些不适合在沙盒中运行的软件有时会出现问题
    - 用于终端程序通常需要执行一些额外步骤
### 什么时候应该安装 flatpak？
- 当软件主要设计为以 Flatpak 运行（例如 Bottles）
- 当你安装不信任的软件时（你可以控制其权限）
- 当它是 GTK/Gnome 应用程序时（因为 Nyarch 自带了它们的运行时，安装很快）
- 当软件不在终端中运行时
### 安装 Flatpak
#### Gnome 软件
你可以使用 **Gnome 软件**来查找、安装、卸载和更新 flatpak 应用程序。

![immagine](https://github.com/user-attachments/assets/34132dbc-f032-475b-90f9-1eec75f1eabd )
![immagine](https://github.com/user-attachments/assets/e2da8b38-7de6-44d3-a045-7a1b5fd4291a )
#### 从 Flathub
你可以在 [Flathub](https://flathub.org/ ) 上找到 flatpaks。从那里安装应用程序会让你的
浏览器下载一个 `.flatpakref` 文件，点击它会在 Gnome 软件中打开应用程序

**注意**：flathub 上的每个应用程序也在 Gnome 软件中
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


## Appimages
**Appimages** 是一种可以在每个 Linux 发行版上运行的特殊格式。
- 优点：
    - 它们可以在*任何* Linux 发行版上运行
- 缺点：
    - 它们不与其他应用程序共享库
    - 它们通常较慢
    - 通常不支持主题

如果存在其他包格式可用，通常不建议使用 appimages。
**仅在没有其他替代方案时使用** appimages。
### 安装和管理 Appimages
下载 appimage 后，你可以双击它，它会启动 **GearLever**。

GearLever 是一个简单的软件，帮助你安装和卸载 appimages。
你可以选择只运行一次 appimage 而不安装，或将其添加到应用程序菜单。

#### 从命令行运行 appimages
你也可以直接从命令行运行 appimage：
1. 赋予它执行权限
```bash
chmod +x application.appimage
```
2. 运行它
```bash
./application.appimage
```

## Arch User Repository
[AUR](https://aur.archlinux.org/ )（Arch 用户仓库）是一个大型的社区驱动的软件包商店，用于 Arch Linux 官方不支持的软件包。**如果某个应用程序存在，你很可能会在 AUR 中找到它。**

Nyarch Linux 完全兼容 AUR，因为它使用默认的 Arch Linux 仓库。

**警告**：AUR 上的软件包由用户上传，因此它们可能不安全。建议始终从软件包构建中检查它们是否可信喵喵喵～。

### 安装软件包
要安装 AUR 软件包，你需要一个 [AUR 助手](https://wiki.archlinux.org/title/AUR_helpers )。

默认情况下，Nyarch Linux 将 `yay` 作为默认 AUR 助手。（或者 `nyay`，因为 neko neko）

要安装 AUR 软件包，你可以运行
```bash
yay -S package
```
例如，
```bash
yay -S zen-browser-bin
```

##### 更新软件包
```bash
yay
```
更新 AUR 中的所有软件包

### 使用 paru 进行
`paru` 是一个功能丰富的 AUR 助手，用 Rust 编写，是 `yay` 的继任者，提供更安全的默认设置和更活跃的维护。

要安装 `paru`，你可以运行：
```bash
sudo pacman -S --needed base-devel git
git clone https://aur.archlinux.org/paru.git
cd paru
makepkg -si
```

##### 使用 paru 安装软件包喵～
`paru` 使用与 `pacman` 类似的语法，使其易于上手。

要安装 AUR 软件包，你可以运行：
```bash
paru -S package
```
例如，
```bash
paru -S chrome
```

##### 更新软件包
```bash
paru
```
或
```bash
paru -Syu
```
这会同时更新官方仓库和 AUR 中的所有软件包 。

##### paru 的小提示
- **推出审阅**：审阅中按q即可推出
- **查看 PKGBUILD**：`paru -Gp package` 可以在安装前查看软件包构建脚本 
- **查看 AUR 评论**：`paru -Gc package` 可以查看其他用户对软件包的评论 
- **交互式搜索**：直接运行 `paru searchterm` 可以交互式搜索并选择安装 
- **跳过审查**：`paru -S package --skipreview`（不推荐用于不信任的软件包）

### 软件包名称指南
你可能会遇到同一程序的多个软件包。这是 Vesktop 的一个示例：
![immagine](https://github.com/user-attachments/assets/e38667d5-a46a-4d39-8205-ad3ee276d90b )

根据后缀：

- `-git`：此软件包是从 Git 仓库中的最新代码构建的。它可能不稳定，但你会获得最新的功能和更新。此外，它会**编译软件包**

- `-bin`：此软件包是二进制软件包，这意味着它是**预编译**的，可以直接使用。你不需要从源代码构建它
- 如果没有后缀，通常意味着该软件包是"发布"版本。换句话说，它是软件的最新稳定版本，没有任何后缀或前缀。
