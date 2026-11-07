# Nvidia サポート
バージョン `24.11.1` から、Nyarch Linux は再び **NVIDIA用の独自ドライバ** を備えた Nyarch バージョンをサポートしています。

**Note:** Nvidia バージョンは RTX5000 GPU をサポートしていません。通常の ISO に `nvidia-open` ドライバを [手動](install_nvidia_drivers.md) でインストールする必要があります。

ハイブリッドグラフィックスを管理するために、[envycontrol](https://github.com/bayasdev/envycontrol) をインストールし、Gnome のシンプルなトグルスイッチで管理します。

**Note:** 仮想マシンに Nyarch をインストールする場合は、通常の Nyarch ISO を使用してください。

## サポートされているGPU

Nvidia ISO は `nvidia` ドライバでまだサポートされているすべての GPU をサポートしているため、`NV110+` は (`NV190/ADXXX`) までです（基本的に GeForce 750 以上の GPU は RTX 5000 まで（RTX5000シリーズは含まれません）、リストは [こちら](https://nouveau.freedesktop.org/CodeNames.html) で確認できます）。

サポートされていないNVIDIA GPUをお持ちの場合、ドライバーを手動でインストールする必要があるかもしれません。

## 手動ドライバーのインストール

ただ、[このガイド](https://github.com/korvahannu/arch-nvidia-drivers-installation-guide) に従ってください。
