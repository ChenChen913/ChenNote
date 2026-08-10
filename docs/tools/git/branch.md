# Git 分支管理

## 创建分支

```bash
git branch feature-xxx
git checkout feature-xxx
# 或者一步到位
git checkout -b feature-xxx
```

## 合并分支

```bash
git checkout main
git merge feature-xxx
```

## 分支策略

- `main` - 主分支，保持稳定
- `develop` - 开发分支
- `feature/*` - 功能分支
- `hotfix/*` - 紧急修复分支
