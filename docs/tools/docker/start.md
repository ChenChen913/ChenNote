# Docker 入门

## 安装

=== "Windows"
    ```powershell
    winget install Docker.DockerDesktop
    ```

=== "macOS"
    ```bash
    brew install --cask docker
    ```

=== "Linux"
    ```bash
    curl -fsSL https://get.docker.com | sh
    ```

## 基本命令

```bash
# 拉取镜像
docker pull nginx

# 运行容器
docker run -d -p 8080:80 nginx

# 查看运行中的容器
docker ps

# 停止容器
docker stop <container-id>
```
