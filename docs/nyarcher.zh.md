# Nyarcher
Nyarcher 是一个 Shell 脚本，用于在许多 Linux 发行版上安装 [Nyarch Linux](https://github.com/NyarchLinux/NyarchLinux ) 的自定义配置

## 免责声明
该脚本旨在尽可能在任何 Linux 发行版上提供与 Nyarch Linux 相似的体验，而不修改系统文件。因此，请阅读[你错过了什么部分](#what-you-are-missing)喵呜～。
此外，某些应用程序，特别是 Nyarch 脚本，可能在非 Arch 基础发行版上无法正常工作。
唯一会修改系统文件的操作都标有 [SYSTEM]。它们并不危险，但你最好知道它们正在执行这些操作。
如果出现问题，通过在你的发行版上创建一个新用户，你将不会受到脚本所做更改的影响，除了标有 [SYSTEM] 的脚本部分所做的更改。

## 安装前置要求
**在任何发行版上，都需要安装 Gnome 47**

### Arch 基础发行版
```bash
sudo pacman -S curl python-pip flatpak gnome-menus kitty wget git fastfetch npm nodejs pacman-contrib gnome-menus gnome-shell-extensions tar
sudo pacman -S python-pywal
```
还建议从 AUR 安装 `webapp-manager` 和 `gnome-terminal-transparency`。

### Fedora 基础发行版
```bash
sudo dnf install curl flatpak python3-pip svn gnome-menus kitty wget git neofetch npm nodejs btop gnome-menus gnome-extensions-app
sudo pip3 install pywal
sudo cp /usr/local/bin/wal /usr/bin/wal
```
注意：wal 需要位于 /usr/bin/wal，这是最后一条命令的原因

### Ubuntu 基础发行版
```bash
sudo apt install curl python3-pip flatpak subversion gnome-menus kitty wget git neofetch npm nodejs btop gnome-menus gnome-shell-extension-prefs
sudo pip3 install pywal
```

## 运行脚本 
如果你想了解脚本的作用，可以阅读 [NYARCHER.md](https://github.com/NyarchLinux/Nyarcher/blob/main/NYARCHER.md ) 文件。
<br />
**注意：脚本会在覆盖之前备份大多数现有配置，此外，除了 /usr/bin/nyaofetch 和 /usr/bin/nekofetch 文件外，它只编辑当前用户的设置**
<br />
下载 `nyarcher.sh` 并添加执行权限，然后执行它
```bash
git clone https://github.com/NyarchLinux/Nyarcher.git 
cd Nyarcher
chmod +x nyarcher.sh
./nyarcher.sh
```
脚本会询问你是否要应用某些设置，**强烈建议对所有选项都说 yes**，以获得稳定的体验。

## What YOu Are Missing
 你错过了什么喵
通过运行此脚本，你不会获得完整的 Nyarch 体验，以下是脚本中缺少但发行版中存在的功能。

请注意，几乎任何这些功能都可以通过运行一些命令或编辑几个文件集成到任何发行版中。

- gnome-terminal-transparency 不会由脚本安装，它是实现透明效果的 Gnome 终端版本。Fedora 用户默认拥有它。你可以从 [AUR](https://aur.archlinux.org/packages/gnome-terminal-transparency ) 安装
- Webapp manager 默认不会安装，你可以从 [AUR](https://aur.archlinux.org/packages/webapp-manager ) 安装
- plymouth（启动动画）不会由此脚本安装，其主题也不会。Plymouth 安装因发行版而异，[这是 Arch Linux 的 wiki 页面](https://wiki.archlinux.org/title/plymouth )。我们使用的主题在[这里](https://github.com/NyarchLinux/NyarchLinux/tree/main/Gnome/usr/share/plymouth/themes )
- 在裸机上安装 Nyarch 的希望不会摧毁你的电脑的勇气
- Calamares 安装程序：仅在 Live ISO 中可用。它是一个几乎标准的 Calamares，带有 adwaita qt 主题，你可以在[这里](https://github.com/NyarchLinux/NyarchLinux/tree/main/Gnome/etc/calamares/branding/ezarcher )找到安装过程中显示的幻灯片。
- `yay`，由脚本安装，它们是 AUR 助手，你可以用另一个 AUR 助手安装它。Yay 也被别名为 `nyay`，因为 ^ ^ 喵
- 你会遇到一些在 Nyarch 上不会出现的预期错误：
  - Pywal 主题默认不会生成，要修复此问题，请重新加载主题（从 Nyarch Customize 更改颜色主题，或者如果你启用了 material you，只需更改壁纸）
  - 运行脚本后你必须注销并重新登录
  - Nyarch Tour 在你重新登录后不会自动启动，请自行运行它
  - Nyarch 更新程序很可能无法正常工作
  - Material You 可能无法在某些发行版（在 Fedora 中遇到）上自动应用 Material You Gnome Shell 主题而不需要注销/登录。尚未找到简单的修复方法。一个无需注销的解决方法是，在 gnome tweaks（或扩展设置）中将 Gnome shell 主题更改为另一个，然后再改回 Material You 主题
