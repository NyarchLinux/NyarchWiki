# アプリケーションのインストール

あなたはNyarch Linuxにおいて複数のアプリケーションインストール方法を選択することが可能です。これを「パッケージングフォーマット」と呼びます。
このページでは、パッケージ形式の違いとそれらのインストールおよび管理方法について説明しています。

サポートされているパッケージ:

1. [Arch Linux Packages](#arch-linux-packages) (pacman, .tar.zst)
2. [Flatpaks](#flatpaks) (Store, .flatpakref, .flatpak)
3. [AppImages](#appimages) (.appimage)
4. [Arch User Repository](#arch-user-repository) (yay & paru)

## Arch Linux Packages 
ほぼすべての Linux ディストリビューションにはパッケージマネージャーがあり、コンピュータ上のパッケージのインストール、削除、更新を支援します。

Arch Linux では、パッケージマネージャは `pacman`です。

様々な理由により、pacmanはターミナル経由及び管理者権限でのみ使用する必要があります。

以下は `pacman` の基本的な使い方です。より詳細な手順をご希望の場合は、[pacman on the Arch Wiki](https://wiki.archlinux.org/title/Pacman )をご確認ください。

### パッケージのインストール方法
```bash
sudo pacman -S package
```
例として、`firefox`をインストールしたい場合、このように入力します
```bash
sudo pacman -S firefox
```

### パッケージを削除する方法
```bash
sudo pacman -R package
```
依存関係も削除したい場合は、`-Rns` を使用できます。

### すべてのパッケージを更新する方法
```bash
sudo pacman -Syu
```
### パッケージの検索方法
```bash
sudo pacman -Ss package
```

## Flatpaks
Flatpak は、**sandboxed** 環境でアプリケーションをインストールできる特別なパッケージングフォーマットです。

これは、スマートフォンで行うように、アプリケーションが持っている権限を簡単に管理できることを意味します。

フラットパックにはいくつかの長所と短所があります。

- 利点：
- すべてのLinuxディストリビューションで動作します
- 権限を管理できます
- ストアから簡単にインストールできます
- 管理者権限なしでアプリケーションをインストールできます
- 欠点：
- ネイティブパッケージに比べて、より多くのディスク容量を占有します。
- サンドボックス内で実行できないソフトウェアに対して、時々問題が生じます。
- ターミナルプログラムで使用する場合、しばしば追加の手順が必要です。
  
### Flatpakはいつインストールすべきですか？
- ソフトウェアが主にFlatpakとして実行されることになっている場合（例：Bottles）
- 信頼できないソフトウェアをインストールする場合（その権限を管理できます）
- GTK/Gnome アプリケーションの場合（Nyarch がランタイムを出荷し、インストールが速いため）
- ソフトウェアが端末で実行されない場合
### Flatpakを使用したインストール
#### Gnome Software
**Gnome Software** を使用して、flatpak アプリケーションを検索、インストール、アンインストール、更新できます。

![immagine](https://github.com/user-attachments/assets/34132dbc-f032-475b-90f9-1eec75f1eabd )
![immagine](https://github.com/user-attachments/assets/e2da8b38-7de6-44d3-a045-7a1b5fd4291a )
#### Flathubからアプリケーションをインストールする
Flatpakは[Flathub](https://flathub.org/)で見つけることができます。そこからアプリケーションをインストールすると、ブラウザが `.flatpakref` ファイルをダウンロードします。これをクリックすると、Gnome Software でアプリケーションが開きます。

**Note**: Flathub のすべてのアプリケーションは Gnome Software にもインストールされています。
#### コマンドライン
```bash
flatpak install application.id
```
例えば、Flatpak を使用して Firefox をインストールする場合
```bash
flatpak install org.mozilla.firefox
```
コマンドラインを使用すれば、`.flatpak` ファイルもインストールできます。
このように実行してください。
```bash
flatpak install file.flatpak
```

また、`.flatpak` ファイルをダブルクリックすると、Gnome Software が開き、インストールできます。

### Flatpak の権限管理
Flatseal を使用して、Flatpak の権限を管理できます。


## Appimages
**Appimages** は、すべての Linux ディストリビューションで実行できる特別なフォーマットです。

- 利点：
- すべてのLinuxディストリビューションで動作します。
- 欠点：
- 他のアプリケーションとライブラリを共有しません。
- 一般的に遅いです。
- 多くの場合、テーミングをサポートしていません。

他に利用可能なパッケージング形式がある場合、一般的にappimagesの使用は推奨されません。
**代替手段がない場合にのみ**、appimages を使用してください。
### Appimages のインストールと管理
Appimage をダウンロードした後、ダブルクリックすると **GearLever** が起動します。

GearLeverは、appimagesのインストールとアンインストールを支援するシンプルなソフトウェアです。
Appimage をインストールせずに一度だけ実行するか、アプリメニューに追加することができます。

#### コマンドラインから appimages を実行する
コマンドラインから直接 appimage を実行することもできます。
1. 実行の許可を与える
```bash
chmod +x application.appimage
```
2. 実行する
```bash
./application.appimage
```

## Arch User Repository
[AUR](https://aur.archlinux.org/) (Arch User Repository) は、Arch Linux が公式にサポートしていないパッケージ向けの大規模なコミュニティ主導ストアです。**アプリケーションが存在する場合、AURで見つかる可能性が非常に高いです。**

Nyarch Linux は、デフォルトの Arch Linux リポジトリを使用しているため、AUR と完全に互換性があります。

**警告**:AUR のパッケージはユーザーによってアップロードされているため、安全ではない可能性があります。パッケージビルドからそれらが信頼できるかどうか、常に確認することが推奨されます。

### AUR を使用したパッケージのインストール
AUR パッケージをインストールするには、[AUR Helper](https://wiki.archlinux.org/title/AUR_helpers) が必要です。

デフォルトでは、Nyarch Linux は `yay` をデフォルトの AUR ヘルパーとして提供します。(または、`nyay` も使えるよ、笑)
AURパッケージをインストールするには、このようにします。
```bash
yay -S package
```
例として:
```bash
yay -S zen-browser-bin
```

#### パッケージの更新
```bash
yay
```
AURからすべてのパッケージを更新します

### Paru を使用

`paru` は、Rust で実装された機能豊富な AUR ヘルパーで、`yay` の後継であり、より安全なデフォルト設定とより積極的なメンテナンスを提供します。

`paru` をインストールするには、次のように実行します:
```bash
sudo pacman -S --needed base-devel git
git clone https://aur.archlinux.org/paru.git 
cd paru
makepkg -si
```

#### Paru を使用したパッケージのインストール
`paru` は `pacman` に似た構文を使用しており、簡単に取得することができます。

AUR パッケージをインストールするには、次のように実行します:
```bash
paru -S package
```
例として:
```bash
paru -S chrome
```

#### パッケージの更新
```bash
paru
```
or
```bash
paru -Syu
```
これは、公式リポジトリとAURの両方からすべてのパッケージを更新します。

#### paruのヒント
- **レビューを終了**: レビュー中に終了するには q を押してください
- **PKGBUILDの表示**: `paru -Gp package` は、インストール前にパッケージビルドスクリプトを表示できます
- **View AUR comments**: `paru -Gc package` は、パッケージに関する他のユーザーのコメントを表示できます
- **インタラクティブ検索**: `paru searchterm` を直接実行すると、インタラクティブに検索でき、インストールを選択できます
- **レビューのスキップ**: `paru -S package --skipreview`（信頼できないパッケージには推奨されません）
### パッケージ名ガイド
同じプログラムに対して複数のパッケージに遭遇する可能性があります。これはVesktopの例です:
![immagine](https://github.com/user-attachments/assets/e38667d5-a46a-4d39-8205-ad3ee276d90b )

サフィックスについて：

- `-git`: このパッケージは、Gitリポジトリの最新コードからビルドされています。安定しているわけではありませんが、最新の機能やアップデートをご利用いただけます。また、それは**パッケージをコンパイルします**
- `-bin`: このパッケージはバイナリパッケージであり、**コンパイル済み**で、すぐに使用できる状態です。ソースから構築する必要はありません
- サフィックスがない場合、通常はパッケージが「リリース」バージョンであることを意味します。言い換えれば、これはソフトウェアの最新の安定版であり、サフィックスやプレフィックスはありません。
