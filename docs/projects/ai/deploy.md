# AI 项目部署文档

## 环境要求

- Python 3.11+
- Docker
- CUDA (可选)

## 部署步骤

```bash
# 1. 克隆代码
git clone <repo-url>
cd voice-ime

# 2. 安装依赖
pip install -r requirements.txt

# 3. 配置
cp .env.example .env
# 编辑 .env 填入你的配置

# 4. 启动
docker-compose up -d
```

## 监控

```bash
# 查看日志
docker-compose logs -f

# 查看状态
docker-compose ps
```
