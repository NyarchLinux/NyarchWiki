# Nvidiaドライバーのインストール

バージョン `24.11.1` から、Nyarch Linux は再び **NVIDIAの独自ドライバー** を備えた Nyarch バージョンをサポートしています。

ただし、Nvidiaバージョンをインストールしていない場合、またはサポートされていないNvidia GPUをお持ちの場合は、ドライバーを手動でインストールする必要があるかもしれません。このガイドは参考程度にしてください。

## インストール

マルチリブリポジトリを有効にする必要があります。そのためには、お好きなテキストエディタで `/etc/pacman.conf` を開き、以下の行のコメントを解除してください。
```bash
[multilib]
Include = /etc/pacman.d/mirrorlist
```

次に、リポジトリとシステムを更新してください。

```bash
sudo pacman -Syu
```

これで、要求されるパッケージをインストールできます。

```bash
sudo pacman -S base-devel linux-headers git nano --needed
```

最新のGPUを使用している平均的なユーザーは、単に `nvidia` パッケージをインストールしてください。

```bash
sudo pacman -S nvidia nvidia-utils
```

ただし、古いGPUをお持ちの場合は、[Arch Wiki guide](https://wiki.archlinux.org/title/NVIDIA)をご参照ください。

## 設定

もし同じ古いWindowsユーザーであれば、Nvidiaコントロールパネルをご存知かもしれません。Linux では、`nvidia-settings` があり、これは Nvidia GPU を構成するためのグラフィカルツールです。

インストールするには、これを実行します。

```bash
sudo pacman -S nvidia-settings
```

その後、ターミナルまたはアプリケーションメニューから実行できます。

Nvidia の自動設定で xorg を構成したい場合は、以下のコマンドを実行してください。
```bash
sudo nvidia-xconfig
```
