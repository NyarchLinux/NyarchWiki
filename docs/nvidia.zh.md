# Nvidia 支持
从 `24.11.1` 版本开始，Nyarch Linux 再次支持**预装 Nvidia 专有驱动**的 Nyarch 版本。

**注意：** Nvidia 版本不支持 RTX5000 GPU。您需要在普通 ISO 上[手动安装](install_nvidia_drivers.md) `nvidia-open` 驱动喵～。

它还将安装 [envycontrol](https://github.com/bayasdev/envycontrol) 来管理混合显卡，在 Gnome 中可以简单切换。

**注意：** 如果您在虚拟机上安装 Nyarch，请使用普通的 Nyarch ISO。

## 支持的 GPU
Nvidia ISO 支持所有仍受 `nvidia` 驱动支持的 GPU，即 `NV110+` 到 (`NV190/ADXXX`)（基本上是 GeForce 750+ GPU 直到 RTX 5000（不包括），您可以在[这里](https://nouveau.freedesktop.org/CodeNames.html)查看列表）。

如果您的 Nvidia GPU 不受支持，您可能需要手动安装驱动程序。

## 手动安装驱动
只需按照[这个指南](https://github.com/korvahannu/arch-nvidia-drivers-installation-guide)操作。
