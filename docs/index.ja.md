# Nyarch Wiki

Nyarch Linux のウィキは、すべてのスキルレベルのユーザー、特にNyarch Linuxが初めてのユーザーにとって、**簡潔・率直・明確** かつ **使いやすい** リソースになるよう設計されています。
包括的な[Arch Wiki](https://wiki.archlinux.org)とは異なり、Nyarch Linux Wikiは、さまざまなトピックに関するよりシンプルで分かりやすい情報の提供に重点を置いています。さらに、Nyarch Linuxの体験を向上させるために、Nyarch 固有の**ガイダンスと推奨事項**を提供しています。

## このWikiには何が含まれていますか？

- 初心者向けの簡単なチュートリアルと提案
- Linux と Arch Linux に関する簡略化された説明（Arch Wiki よりも簡易ですが、リンクも提供しています）
- Nyarch固有の使用提案

## このWikiに含まれないものは何ですか？

- サーバーに関すること
- 高度なトピックまたは危険なトピック
- 詳細な技術的説明

## Wikiへの貢献

[GitHub](https://github.com/NyarchLinux/NyarchWiki)のWikiに貢献できます。
Wikiに貢献するには、GitHubアカウントにログインし、リポジトリをご訪問ください。

このWikiは[Mkdocs](https://www.mkdocs.org/)を使用して構築されています。

すべてのコンテンツファイルは `docs/` にあります。新しいページを作成するには、そのフォルダーにMarkdownファイルを作成し、`mkdocs.yml` ファイルのインデックスに追加してください。
Git を使用してコンピュータ上でリポジトリ全体をクローンするか、GitHub WebUI から直接Wikiを編集するかを選択できます。

### Github WebUI から Wiki に貢献する
まず、GitHubページの上部にあるボタンを使用してWikiをフォークしてください。

![immagine](https://github.com/user-attachments/assets/b8cffa4c-fe3f-470b-9163-65e328dfbf42)

フォークが作成されたら、GitHub WebUI を開き、鉛筆アイコンをクリックすることで、直接ファイルを編集できます。

![immagine](https://github.com/user-attachments/assets/71e34d22-4787-4db8-96dd-dab20b142938)

こちらで変更を行い、プレビューすることができます。

![immagine](https://github.com/user-attachments/assets/e9bfdf92-3968-423a-a9d0-afff133e2acc)

適切な変更を行った後、**commit changes** をクリックし、変更した内容の概要を書いてください。
![immagine](https://github.com/user-attachments/assets/2666e96f-75f9-4374-bd72-621e900c71c4)

その後、**X commits ahead of...** をクリックしてpull requestを開いてください。

![immagine](https://github.com/user-attachments/assets/b411b295-8dcf-4777-ac18-fd1c8ffdd772)

pull requestを作成し、すべての変更点を説明してください。変更内容を確認し、適切な修正を求め、受け入れます。
## Wikiのデプロイ
まず、Wikiをクローンします。
```bash
git clone https://github.com/NyarchLinux/NyarchWiki
```

Python venv に mkdocs と mkdocs-material をインストールします。
```bash
python -m venv venv
source venv/bin/activate
pip install mkdocs mkdocs-material
```
Wikiを起動します:
```bash
mkdocs serve
```
