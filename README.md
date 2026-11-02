# user-man

用户手册文档项目，使用 Sphinx 构建，使用 Pandoc 转换文档格式。

## 安装

需要 Python 3.11+ 和 Pandoc（Debian/Ubuntu 可使用 `sudo apt-get update && sudo apt-get install -y pandoc`）。

```sh
python3 -m venv .venv
.venv/bin/python -m pip install -r requirements-docs.txt
```

## 构建文档

```sh
.venv/bin/sphinx-build -W --keep-going -b html docs _build/html
```

生成的入口为 `_build/html/index.html`。

## Pandoc 转换示例

```sh
mkdir -p _build
pandoc README.md --standalone --metadata title=user-man -o _build/readme.html
```

PDF 导出需要另行安装对应的 PDF 引擎。
