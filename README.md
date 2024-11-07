# Nyarch Wiki
The Nyarch Linux wiki is designed to be a **straightforward** and **accessible** resource for users of all skill levels, particularly those new to Nyarch Linux.
Unlike the comprehensive [Arch Wiki](https://wiki.archlinux.org), the Nyarch Linux Wiki focuses on providing **simpler, easy-to-understand information on various topics**. Additionally, it offers Nyarch-specific **guidance and recommendations** to help you enhance your experience with Nyarch Linux.

## Contributing to the Wiki

You can contribute to the wiki on [GitHub](https://github.com/NyarchLinux/NyarchWiki).

## Deploying the wiki
Firstly, clone the wiki:
```bash
git clone https://github.com/NyarchLinux/NyarchWiki
```

Install mkdocs and mkdocs-material in a python venv
```bash
python -m venv venv
source venv/bin/activate
pip install mkdocs mkdocs-material
```
Launch the wiki:
```bash
mkdocs serve
```
