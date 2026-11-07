# 在 Nyarch Linux 上运行 Windows 游戏

在 Nyarch Linux 上玩 Windows 游戏，主要有三条路径：**Steam + Proton**、**Bottles** 和 **Lutris**。三者各有分工，并不互斥，很多猫猫会同时用其中两个甚至三个喵～

本页只介绍在 Nyarch 上实际可用的方案和安装方式。如果你的游戏在 Steam 上，优先用 Steam；如果游戏来自 GOG、Epic、itch.io 或独立安装包，Bottles 或 Lutris 会更合适。

## Steam + Proton

如果你主要在 Steam 上买游戏，这是最省心的方式。Proton 是 Valve 基于 Wine 开发的兼容层，直接内置于 Steam 客户端，不需要单独“安装”。

### 在 Nyarch 上安装 Steam

Nyarch 默认启用了 Flathub，因此最直接的方式是通过 Flatpak 安装 Steam：

```bash
flatpak install flathub com.valvesoftware.Steam
```

也可以用 Arch 仓库的 `steam` 包（需要启用 `multilib` 仓库）：

```bash
sudo pacman -S steam
```

此外，你也可以安装 **steam-native-runtime**（AUR），通过 `steam-native` 启动由原生系统库驱动的 Steam。

**注意：** Steam Flatpak 自带打过补丁的 glibc，某些游戏在原生包下无法启动时，Flatpak 版本反而可能解决问题。

### 启用 Proton

安装 Steam 后，打开 **Steam > 设置 > 兼容性**，勾选“**为所有其他产品启用 Steam Play**”。这样即使游戏没有被 Valve 官方标记为兼容，Steam 也会用 Proton 尝试运行。

对单个游戏，也可以在游戏属性的“兼容性”页中强制指定一个 Proton 版本。

## Bottles

Bottles 是一个 Wine prefix 管理器，适合运行非 Steam 游戏、独立安装包、GOG 离线安装程序，或者你想为每个游戏隔离 Wine 环境的场景。

Bottles 的开发者**强烈建议通过 Flatpak 安装**，因为 Flatpak 版本才能利用沙盒隔离。

```bash
flatpak install flathub com.usebottles.bottles
```

也可以从 Flathub 页面或 GNOME 软件 / Bazaar 中点击安装。值得一提的是，Nyarch 的 Flatpak 教程里也把 Bottles 作为“适合用 Flatpak 安装”的典型例子。

Bottles 的核心概念是 **Bottle**（瓶子）：每个 Bottle 是一个独立的 Wine 前缀，可以单独配置 Windows 版本、DXVK、VKD3D、依赖项等。你不需要在系统层面“安装 Wine”，Bottles 会自己管理所需的 Wine 版本和运行库。

## Lutris

Lutris 更适合“一个地方管理所有启动器”的场景：GOG、Epic、Battle.net、模拟器、独立安装包，以及社区维护的安装脚本。

在 Nyarch 上，Lutris 有两种安装方式。通过 Flatpak 安装：

```bash
flatpak install flathub net.lutris.Lutris
```

或者从 Arch 仓库安装：

```bash
sudo pacman -S lutris
```

需要注意的是，如果你主要用 Lutris 跑需要 GE-Proton 的游戏，**原生（Arch 仓库）的 Lutris 包可能更稳妥**；如果你只是用 Lutris 管理 Wine-GE 或普通 Wine 游戏，Flatpak 版本通常没有问题。

## 兼容层管理工具：ProtonUp-Qt 与 ProtonPlus

无论你用 Steam、Bottles 还是 Lutris，都可能需要 GE-Proton、Wine-GE 或 Luxtorpeda 这类社区兼容层。手动下载和放置这些工具比较麻烦，可以用 ProtonUp-Qt 与 ProtonPlus 这两个图形化管理器。

如果你同时用 Steam 和 Lutris，ProtonUp-Qt 的覆盖面就已经足够使用了。

### ProtonUp-Qt

ProtonUp-Qt 支持 Steam、Lutris 和 Heroic，可以安装、更新和移除 Proton-GE、Wine-GE、Luxtorpeda 等。它通过 Flathub 分发：

```bash
flatpak install flathub net.davidotek.pupgui2
```

### ProtonPlus

ProtonPlus 是另一个现代化兼容层管理器，支持的启动器更广（Steam、Lutris、Heroic、Bottles、WineZGUI），同样可以通过 Flathub 安装：

```bash
flatpak install flathub com.vysp3r.ProtonPlus
```
