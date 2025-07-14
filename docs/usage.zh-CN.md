# OpenDeepWiki 使用指南

本文档介绍如何在本地快速部署并运行 OpenDeepWiki，并提供云端一键部署方式。

## 先决条件
- 已安装 **Docker** 与 **Docker Compose**
- （可选）已安装 **make**
- 编译环境要求：
  - **.NET SDK 9** (预览版)
  - **Node.js 18** 或更高版本，推荐使用自带的 **npm**

## 快速启动

1. 克隆仓库

```bash
git clone https://github.com/AIDotNet/OpenDeepWiki.git
cd OpenDeepWiki
```

2. 根据需要修改 `docker-compose.yml` 中的环境变量，例如 `CHAT_API_KEY`、`CHAT_MODEL` 等。

3. 构建并启动服务

- 使用 **make**（推荐）

```bash
make build
make up
```

- 或直接使用 **Docker Compose**

```bash
docker-compose build
docker-compose up -d
```

4. 浏览器访问 `http://localhost:8090` 即可开始使用。

## 从源码编译

如需自行构建前后端，可执行以下脚本：

- **Linux/macOS**

```bash
./build.sh
```

- **Windows**

```cmd
build.bat
```

该脚本会自动执行 `dotnet publish` 与 `npm run build`，并在 `output/` 目录生成编译好的后端与前端文件。


## 一键部署到 Sealos

若希望在云端快速部署，可通过 Sealos 模板实现一键部署。点击下方按钮并按照页面提示操作：

[![Deploy on Sealos](https://raw.githubusercontent.com/labring-actions/templates/main/Deploy-on-Sealos.svg)](https://bja.sealos.run/?openapp=system-template%3FtemplateName%3DOpenDeepWiki)

详细步骤可查看 [scripts/sealos/README.zh-CN.md](../scripts/sealos/README.zh-CN.md)。

---

更多高级配置与原理说明请参阅根目录的 [README.zh-CN.md](../README.zh-CN.md)。
