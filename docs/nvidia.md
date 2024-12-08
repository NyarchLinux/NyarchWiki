# Nvidia Support
Starting from version `24.11.1`, Nayrch Linux supports again a Nyarch version with **nvidia proprietary drivers preinstalled**.

It will also install [envycontrol](https://github.com/bayasdev/envycontrol) to manage hybrid graphics, with a simple toggle in Gnome.

**Note:** If you are installing Nyarch on a virtual machine, use the normal Nyarch ISO.

## Supported GPUS
Nvidia ISO supports every GPU still supported by the official driver, so `NV110+` GPUs (basically GeForce 750+ GPUs, you can check the list [here](https://nouveau.freedesktop.org/CodeNames.html)).

If you have a not supported nvidia GPU, you might have to install the drivers manually.

## Manual driver installation
Just follow [this](https://github.com/korvahannu/arch-nvidia-drivers-installation-guide).

