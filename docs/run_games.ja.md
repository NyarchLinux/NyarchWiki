# Nyarch Linux で Windows ゲームを遊ぶ

Nyarch Linux で Windows ゲームを遊ぶ方法は、主に **Steam + Proton**、**Bottles**、**Lutris** の 3 つです。それぞれにそれぞれの強みがあり、2つ、あるいは 3つすべてを併用している人も多くいます。

このページでは、Nyarch 上で実際に使える方法と、そのインストール手順だけを紹介します。Steam で購入したゲームなら Steam を優先してください。GOG、Epic、itch.io、単体のインストーラーから入手したゲームなら、Bottles か Lutris のほうが向いています。

## Steam + Proton

Steam でゲームを買うことが多いなら、これが一番手間のかからない方法です。Proton は Valve が Wine をベースに開発した互換レイヤーで、Steam クライアントに同梱されているため別途インストールする必要はありません。

### Nyarch に Steam をインストールする

Nyarch では Flathub が最初から有効になっているので、Flatpak で Steam をインストールするのが最も簡単です：

```bash
flatpak install flathub com.valvesoftware.Steam
```

Arch リポジトリの `steam` パッケージを使うこともできます（`multilib` リポジトリを有効にする必要があります）：

```bash
sudo pacman -S steam
```

**steam-native-runtime**（AUR）をインストールして、`steam-native` からシステムのネイティブライブラリで Steam を起動することもできます。

**注意：** Steam の Flatpak 版は独自にパッチを当てた glibc を同梱しています。ネイティブパッケージでは起動しないゲームが、Flatpak 版なら動く場合があります。

### Proton を有効にする

Steam をインストールしたら、**Steam > 設定 > 互換性** を開き、「**他のすべてのタイトルで Steam Play を有効にする**」にチェックを入れます。これで Valve が互換性ありとしていないゲームも、Steam が Proton で起動を試みます。

ゲームごとに、プロパティの「互換性」タブで特定の Proton バージョンを指定することもできます。

## Bottles

Bottles は Wine プレフィックスの管理ツールです。Steam 以外のゲーム、単体のインストーラー、GOG のオフラインインストーラー、あるいはゲームごとに Wine 環境を分離したい場合に向いています。

Bottles の開発者は**Flatpak でのインストールを強く推奨しています**。サンドボックスによる分離を利用できるのは Flatpak 版だけだからです。

```bash
flatpak install flathub com.usebottles.bottles
```

Flathub のページや、GNOME ソフトウェア / Bazaar からクリックしてインストールすることもできます。Nyarch の Flatpak ガイドでも、Bottles は「Flatpak 向きの代表例」として挙げられています。

Bottles の中心となる概念は **Bottle**（ボトル）です。各 Bottle は独立した Wine プレフィックスで、Windows のバージョン、DXVK、VKD3D、依存関係などを個別に設定できます。システム全体に「Wine をインストール」する必要はなく、Bottles が必要な Wine のバージョンとランタイムをBottles 自身が管理することが出来ます。

## Lutris

Lutris は「すべてのランチャーを 1 か所で管理する」用途に向いています。例えばGOG、Epic、Battle.net、エミュレーター、単体のインストーラー、そしてコミュニティが保守しているインストールスクリプトといった形式に対応しています。

Nyarch では Lutris を 2 通りの方法でインストールできます。Flatpak の場合：

```bash
flatpak install flathub net.lutris.Lutris
```

Arch リポジトリからインストールする場合：

```bash
sudo pacman -S lutris
```

GE-Proton が必要なゲームを Lutris で動かすことが多いなら、**ネイティブ（Arch リポジトリ）の Lutris パッケージのほうが安全**です。Wine-GE や通常の Wine のゲームを管理するだけなら、Flatpak 版でも通常は問題ありません。

## 互換レイヤー管理ツール：ProtonUp-Qt と ProtonPlus

Steam、Bottles、Lutris のどれを使う場合でも、GE-Proton、Wine-GE、Luxtorpeda といったコミュニティ製の互換レイヤーが必要になることがあります。手動でダウンロードして配置するのは面倒なので、ProtonUp-Qt と ProtonPlus という 2 つの GUI 管理ツールを使うと便利です。

Steam と Lutris だけを使っているなら、ProtonUp-Qt で十分にまかなえます。一方、Bottles を使用する場合はProtonPlus が必要です。

### ProtonUp-Qt

ProtonUp-Qt は Steam、Lutris、Heroic に対応し、Proton-GE、Wine-GE、Luxtorpeda などのインストール・更新・削除ができます。Flathub で配布されています：

```bash
flatpak install flathub net.davidotek.pupgui2
```

### ProtonPlus

ProtonPlus はもう 1 つのモダンな互換レイヤー管理ツールで、対応ランチャーがより広く（Steam、Lutris、Heroic、Bottles、WineZGUI）、こちらも Flathub からインストールできます：

```bash
flatpak install flathub com.vysp3r.ProtonPlus
```


