# MCBBBS 玩家百科（MkDocs）

本项目由原有的两个独立 HTML Wiki 页面迁移而来，使用 Material for MkDocs 构建，并可由 GitHub Actions 自动部署到 GitHub Pages。

## 页面

- `docs/index.md`：MCBBBS 粘液生存服务器玩家手册
- `docs/slimefun-addons.md`：粘液科技扩展玩法指南

## 本地预览

需要 Python 3.9 或更高版本。

```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
python -m pip install -r requirements.txt
mkdocs serve
```

浏览器打开 `http://127.0.0.1:8000/`。生成静态文件可执行：

```powershell
mkdocs build --strict
```

## 部署到 GitHub Pages

1. 新建 GitHub 仓库，将本目录中的全部文件提交并推送到 `main` 分支。
2. 打开仓库的 **Settings → Pages**。
3. 将 **Build and deployment → Source** 设为 **Deploy from a branch**。
4. 选择 `gh-pages` 分支和 `/ (root)`，保存。
5. 推送后，`.github/workflows/deploy.yml` 会自动构建并更新 `gh-pages` 分支。

站点地址：[https://dac114514.github.io/mcbbbs-docs/](https://dac114514.github.io/mcbbbs-docs/)。

## 编辑内容

直接编辑 `docs` 下的 Markdown 文件即可。原 HTML 的表格、提示框、折叠问答和主要站内锚点已经迁移；中文搜索由 `jieba` 提供分词支持。
