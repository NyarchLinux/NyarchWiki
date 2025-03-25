# Install Nvidia Drivers

Starting from version `24.11.1`, Nayrch Linux supports again a Nyarch version with **nvidia proprietary drivers preinstalled**.

However, if you have not installed the Nvidia version, or you have a not supported Nvidia GPU, you might have to install the drivers manually, and this guide is for you.

## Installation

You will need to have the multilib repository enabled. To do so, open `/etc/pacman.conf` with your favorite text editor and uncomment the following lines:

```bash
[multilib]
Include = /etc/pacman.d/mirrorlist
```

Then, update the repositories, and your system:

```bash
sudo pacman -Syu
```

Now, you can install the requirements:

```bash
sudo pacman -S base-devel linux-headers git nano --needed
```

For an average user with a modern gpu, simply install the `nvidia` package:

```bash
sudo pacman -S nvidia nvidia-utils
```

However, if you have an older GPU, please refer to the [Arch Wiki guide](https://wiki.archlinux.org/title/NVIDIA).

## Configuration

If you are a fellow old Windows user, you may know the Nvidia Control Panel. In Linux, we have `nvidia-settings`, which is a graphical tool to configure your Nvidia GPU.

To install it, simply run:

```bash
sudo pacman -S nvidia-settings
```

Then, you can run it from the terminal or from the application menu.

If you want to configure xorg with nvidia's automatic configuration, simply run the following command:

```bash
sudo nvidia-xconfig
```

