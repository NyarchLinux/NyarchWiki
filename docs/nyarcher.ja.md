# Nyarcher
Nyarcher は、多くのLinuxディストリビューションで[Nyarch Linux](https://github.com/NyarchLinux/NyarchLinux)のカスタマイズをインストールするためのシェルスクリプトです。

## 免責条項

このスクリプトは、システムファイルを編集することなく、あらゆる Linux ディストリビューション上で Nyarch Linux に最も類似した体験を提供することを目指しています。これらの理由から、[欠けている箇所](#欠けているもの)をご覧ください。

また、特に Nyarch Scripts の一部のアプリケーションは、非 Arch ベースのディストリビューションでは正しく動作しない可能性があります。

システムファイルを編集する唯一の操作は、[SYSTEM]でフラグが付けられています。危険ではありませんが、スクリプトが行っていることは知っておくべきです。

何か問題が発生した場合、ディストリビューションに新しいユーザーを作成すれば、スクリプトが行う変更（[SYSTEM] とフラグ付けされたスクリプトの一部による変更を除く）の影響を受けません。

## 事前依存関係をインストールする

どのディストリビューションでも、Gnome 47 のインストールが必要です。

### Archベースのディストリビューション
```bash
sudo pacman -S curl python-pip flatpak gnome-menus kitty wget git fastfetch npm nodejs pacman-contrib gnome-menus gnome-shell-extensions tar
sudo pacman -S python-pywal
```
AUR から `webapp-manager` と `gnome-terminal-transparency` をインストールすることも推奨されています。

### Fedoraベースのディストリビューション
```bash
sudo dnf install curl flatpak python3-pip svn gnome-menus kitty wget git neofetch npm nodejs btop gnome-menus gnome-extensions-app
sudo pip3 install pywal
sudo cp /usr/local/bin/wal /usr/bin/wal
```

注意：wal は /usr/bin/wal に含める必要があります。これは最後のコマンドの理由です。
### Ubuntuベースのディストリビューション
```bash
sudo apt install curl python3-pip flatpak subversion gnome-menus kitty wget git neofetch npm nodejs btop gnome-menus gnome-shell-extension-prefs
sudo pip3 install pywal
```
## スクリプトを実行しています

スクリプトが何をするか知りたい場合は、[NYARCHER.md](https://github.com/NyarchLinux/Nyarcher/blob/main/NYARCHER.md) ファイルをご覧ください。

<br/>
※このスクリプトは、上書きする前にほとんどの既存設定をバックアップし、/usr/bin/nyaofetch および /usr/bin/nekofetch ファイルを除外し、現在のユーザーの設定のみを編集します。
<br/>

`nyarcher.sh` をダウンロードし、実行権限を追加してから実行してください。

```bash
git clone https://github.com/NyarchLinux/Nyarcher.git
cd Nyarcher
chmod +x nyarcher.sh
./nyarcher.sh
```

スクリプトは、設定を適用したいかどうかを尋ねます。安定した体験を得るために、**すべてに「はい」と答えることを強く推奨します**。

## 欠けているもの
このスクリプトを実行しても、Nyarch の完全な体験は提供されません。スクリプトに欠けている点はありますが、ディストロには存在します。

ほとんどすべてのものは、いくつかのコマンドを実行したり、いくつかのファイルを編集することで、任意のディストリビューションに統合できることに注意してください。

- gnome-terminal-transparency はスクリプトによってインストールされていません。これは、透明性を実装した Gnome Terminal のバージョンです。Fedora ユーザーはデフォルトでそれを持っています。[AUR](https://aur.archlinux.org/packages/gnome-terminal-transparency)からインストールできます。
- Webapp manager はデフォルトではインストールされていません。[AUR](https://aur.archlinux.org/packages/webapp-manager) からインストールできます。
- plymouth（ブートアニメーション）はこのスクリプトでも、そのテーマでもインストールされていません。Plymouth のインストールは非常にディストリビューション固有です。[Arch LinuxのWikiページ](https://wiki.archlinux.org/title/plymouth)
- 私たちが使用しているテーマは[こちら](https://github.com/NyarchLinux/NyarchLinux/tree/main/Gnome/usr/share/plymouth/themes)です。
- 裸の金属にNyarchを取り付けて、PCを壊さないことを願っています。
- Calamares のインストール: ライブ ISO でのみ利用可能です。これはほぼ標準的な Calamares で、adwaita の Qt テーマです。インストール時に表示されるスライドは、[こちら](https://github.com/NyarchLinux/NyarchLinux/tree/main/Gnome/etc/calamares/branding/ezarcher)でご確認いただけます。

- `yay`、スクリプトによってインストールされ、AURヘルパーです。別のAURヘルパーでインストールできます。Yay は `nyay` とエイリアスされているんだ、笑
- Nyarchでは経験されない予期されるバグがいくつか発生します：
- Pywal テーマはデフォルトでは生成されません。これを修正するには、テーマを再読み込みしてください（Nyarch Customize からカラーテーマを変更するか、設定済みのマテリアルがある場合は壁紙を変更してください）。
- スクリプトを実行した後、ログアウトしてから再度ログインしてください。
- Nyarch Tourは再度ログインすると起動しませんので、ご自身で実行してください。
- Nyarch アップデータが正しく動作しない可能性が非常に高いです。
- Material You は、Fedoraなどの一部ディストロで遭遇した問題で、ログイン/ログアウトせずに自動的に Material You Gnome Shell テーマを適用できない可能性があります。簡単な解決策はまだ見つかっていません。ログアウトせずに作業する作業は、gnome tweaks（または拡張機能の設定）で Gnome シェルのテーマを別のものに変更し、Material You テーマに戻すことです。
