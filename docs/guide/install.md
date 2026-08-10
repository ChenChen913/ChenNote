# 安装说明

## 环境要求

- Python 3.8+
- pip 包管理器

## 安装步骤

### 1. 安装 MkDocs Material

```bash
pip install mkdocs-material
```

### 2. 创建新项目

```bash
mkdocs new my-project
cd my-project
```

### 3. 配置主题

编辑 `mkdocs.yml`，设置主题为 `material`：

```yaml
theme:
  name: material
```

### 4. 启动预览

```bash
mkdocs serve
```

打开浏览器访问 `http://127.0.0.1:8000` 即可预览。

!!! tip "提示"
    使用 `mkdocs serve` 时，每次保存 Markdown 文件都会自动刷新页面。
