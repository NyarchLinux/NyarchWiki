# 安装 Nvidia 驱动

从 `24.11.1` 版本开始，Nyarch Linux 再次支持**预装 Nvidia 专有驱动**的 Nyarch 版本喵～。

但是，如果您没有安装 Nvidia 版本，或者您的 Nvidia GPU 不受支持，您可能需要手动安装驱动程序，本指南适合你喵～。

## 安装

您需要启用 multilib 仓库。为此，请使用您喜欢的文本编辑器打开 `/etc/pacman.conf` 并取消注释以下行：

```bash
[multilib]
Include = /etc/pacman.d/mirrorlist
```

然后，更新仓库和您的系统：

```bash
sudo pacman -Syu
```

现在，您可以安装所需的软件包：

```bash
sudo pacman -S base-devel linux-headers git nano --needed
```

对于拥有现代 GPU 的普通用户，只需安装 `nvidia` 软件包：

```bash
sudo pacman -S nvidia nvidia-utils
```

但是，如果您有较旧的 GPU，请参考 [Arch Wiki 指南](https://wiki.archlinux.org/title/NVIDIA)。

## 配置

如果您是前 Windows 猫，您可能知道 Nvidia 控制面板。在 Linux 中，我们有 `nvidia-settings`，这是一个用于配置 Nvidia GPU 的图形工具。

要安装它，只需运行：

```bash
sudo pacman -S nvidia-settings
```

然后，您可以从终端或应用程序菜单运行它。

如果您想使用 Nvidia 的自动配置来配置 xorg，只需运行以下命令：

```bash
sudo nvidia-xconfig
```
