# ChenNote 📘

个人文档管理中心，基于 **MkDocs Material** 构建，托管在 GitHub Pages。

- 线上地址：https://chenchen913.github.io/ChenNote/
- 仓库地址：https://github.com/ChenChen913/ChenNote

---

## 快速开始

### 1. 环境要求

- Python 3.8+
- Git

### 2. 安装依赖

```bash
pip install mkdocs-material mkdocs-git-revision-date-localized-plugin mkdocs-git-authors-plugin
```

### 3. 本地预览

```bash
cd my-docs
mkdocs serve
```

浏览器打开 http://127.0.0.1:8000 即可预览。**保存 Markdown 文件后页面自动刷新。**

---

## 如何添加新文档

### 1. 创建 Markdown 文件

在 `docs/` 目录下创建 `.md` 文件，例如新建 `docs/学习笔记/Python.md`：

```markdown
# Python 学习笔记

这里是笔记内容...
```

### 2. 注册到导航

编辑 `mkdocs.yml`，在 `nav` 部分加入新条目：

```yaml
nav:
  - 学习笔记:
    - Python: 学习笔记/Python.md
```

### 3. 推送发布

```bash
git add -A
git commit -m "添加 Python 学习笔记"
git push
```

推送后 GitHub Actions 会自动构建并部署，约 1 分钟后线上更新。

---

## 项目结构

```
my-docs/
├── mkdocs.yml              # 站点配置（主题、导航、插件）
├── docs/                   # 所有 Markdown 文档（写在这里）
│   ├── index.md            # 首页
│   ├── stylesheets/
│   │   └── extra.css       # 自定义样式
│   └── ...                 # 你的文档
├── theme/
│   ├── main.html           # 页面模板覆盖（作者信息、评论）
│   └── partials/
│       └── comments.html   # Giscus 评论区配置
└── .github/
    └── workflows/
        └── ci.yml          # 自动部署配置
```

---

## 常用操作

### 日常更新文档

```bash
mkdocs serve        # 本地预览
# 写文档...
git add -A && git commit -m "更新" && git push   # 发布
```

### 修改主题颜色

编辑 `mkdocs.yml` 中 `theme.palette` 的 `primary`：

```yaml
palette:
  - scheme: default
    primary: light blue    # 天蓝
```

可选颜色：`red, pink, purple, indigo, blue, light blue, cyan, teal, green, lime, yellow, amber, orange, deep orange, brown, grey, blue grey, black, white`

### 修改导航结构

`mkdocs.yml` 的 `nav` 部分，支持多级嵌套：

```yaml
nav:
  - 首页: index.md
  - 工具:
    - Git:
      - 基础: tools/git/basics.md
      - 进阶: tools/git/branch.md
```

### 修改自定义样式

编辑 `docs/stylesheets/extra.css`，保存后本地预览自动生效。

---

## 评论区（Giscus）配置说明

评论区目前是占位符状态（`theme/partials/comments.html` 中是 `YOUR_USERNAME/YOUR_REPO`）。

启用步骤：

1. 打开仓库 https://github.com/ChenChen913/ChenNote → **Settings** → **General** → 勾选 **Discussions**
2. 访问 https://github.com/apps/giscus 安装 Giscus App（选 ChenNote 仓库）
3. 访问 https://giscus.app/zh-CN 按提示生成配置
4. 把生成的 `data-repo`、`data-repo-id`、`data-category`、`data-category-id` 替换到 `theme/partials/comments.html` 中
5. 推送后评论区即可用 GitHub 账号登录发言

---

## 部署原理

每次 `git push` 触发 `.github/workflows/ci.yml`：

1. 检出代码 → 安装依赖
2. `mkdocs build` 生成静态文件到 `site/`
3. 上传到 GitHub Pages → 发布

无需手动构建，纯自动。

---

## 常见问题

**Q: 线上更新后看不到变化？**
A: 等 1-2 分钟（Actions 构建时间），然后强制刷新浏览器（Ctrl+F5）。

**Q: 想改站点标题？**
A: 改 `mkdocs.yml` 的 `site_name`。

**Q: 想换暗色模式配色？**
A: `palette` 里 `scheme: slate` 下的 `primary` 单独设置即可。
