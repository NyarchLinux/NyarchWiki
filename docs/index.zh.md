# Nyarch Wiki

Nyarch Linux Wiki 旨在为所有技能水平的用户提供**简单明了**且**易于访问**的资源，特别是对 Nyarch Linux 新手用户。
与全面的 [Arch Wiki](https://wiki.archlinux.org) 不同，Nyarch Linux Wiki 专注于提供**更简单、易于理解的各种主题信息**。此外，它还提供 Nyarch 特定的**指导和建议**，帮助您提升 Nyarch Linux 的使用体验喵～。

## 本 Wiki 包含的内容

- 面向初学者的简单教程和建议
- 关于 Linux 和 Arch Linux 的简化说明（比 Arch Wiki 更简单，但也提供相关链接）
- Nyarch 特定的使用建议

## 本 Wiki 不包含的内容

- 服务器相关内容
- 高级或危险的主题
- 详细的技术说明

## 为 Wiki 做贡献

您可以在 [GitHub](https://github.com/NyarchLinux/NyarchWiki) 上为 Wiki 做贡献。
要为 Wiki 做贡献，请登录您的 GitHub 账户并访问我们的仓库。

本 Wiki 使用 [Mkdocs](https://www.mkdocs.org/) 构建。

所有内容文件都在 `docs/` 目录中。要创建新页面，请在该文件夹中创建一个 markdown 文件，并将其添加到 `mkdocs.yml` 文件的索引中。

您可以选择使用 git 将整个仓库克隆到您的计算机上，或直接从 GitHub WebUI 编辑 Wiki。

### 从 Github WebUI 为 Wiki 做贡献
首先，使用 GitHub 页面顶部的按钮 fork 这个 Wiki。

![immagine](https://github.com/user-attachments/assets/b8cffa4c-fe3f-470b-9163-65e328dfbf42)

Fork 创建后，您可以通过打开文件并点击铅笔图标直接从 Github WebUI 编辑文件。

![immagine](https://github.com/user-attachments/assets/71e34d22-4787-4db8-96dd-dab20b142938)

在这里您可以进行更改并预览它们。

![immagine](https://github.com/user-attachments/assets/e9bfdf92-3968-423a-a9d0-afff133e2acc)

完成适当的更改后，点击 **commit changes** 并写下您修改内容的摘要。
![immagine](https://github.com/user-attachments/assets/2666e96f-75f9-4374-bd72-621e900c71c4)

之后，点击 "X commits ahead of..." 来打开一个 Pull Request

![immagine](https://github.com/user-attachments/assets/b411b295-8dcf-4777-ac18-fd1c8ffdd772)

创建一个 Pull Request 并解释您的所有更改。我们将审查您的更改，要求适当的修改并接受它们。

## 部署 Wiki
首先，克隆 Wiki：
```bash
git clone https://github.com/NyarchLinux/NyarchWiki
```

在 Python 虚拟环境中安装 mkdocs 和 mkdocs-material
```bash
python -m venv venv
source venv/bin/activate
pip install mkdocs mkdocs-material mkdocs-static-i18n
```
启动 Wiki：
```bash
mkdocs serve
```
