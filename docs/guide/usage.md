# 使用教程

## 编写文档

所有文档放在 `docs/` 目录下，用 Markdown 格式编写。

### 基本语法

```markdown
# 一级标题
## 二级标题
### 三级标题

**粗体** *斜体* `行内代码`

- 无序列表
- 无序列表

1. 有序列表
2. 有序列表

[链接文字](https://example.com)
![图片描述](image.png)
```

### 代码块

带语法高亮的代码块：

```python
def hello():
    print("Hello, MkDocs!")
```

### 提示框

Material 主题支持多种提示框：

!!! note "注意"
    这是一条注意事项。

!!! warning "警告"
    这是一条警告信息。

!!! danger "危险"
    这是一个危险操作提示。

## 添加新页面

1. 在 `docs/` 下创建 `.md` 文件
2. 在 `mkdocs.yml` 的 `nav` 中添加导航条目
3. 保存后自动更新
