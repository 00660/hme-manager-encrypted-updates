# hme-manager-encrypted-updates

HME 加密发布仓库，只发布：

- `update_manifest.json`
- 加密后的原生部署 zip
- `install.sh` 一键部署脚本

不会发布：

- Python 源码
- 明文 payload
- 构建工作目录

## 一键部署

最新版安装：

```bash
curl -fsSL https://github.com/00660/hme-manager-encrypted-updates/raw/refs/heads/main/install.sh | sudo bash -s --
```

指定网络授权 API：

```bash
curl -fsSL https://github.com/00660/hme-manager-encrypted-updates/raw/refs/heads/main/install.sh | sudo bash -s -- --license-api-url https://your-license-api.example
```

指定面板端口：

```bash
curl -fsSL https://github.com/00660/hme-manager-encrypted-updates/raw/refs/heads/main/install.sh | sudo bash -s -- --web-port 8790
```

脚本行为：

- 自动安装 Docker（若系统未安装）
- 下载最新加密发布包
- 部署到 `/opt/hme-manager`
- 保留已有 `runtime` 数据目录
- 自动执行 `docker compose up -d --build`

## 仓库信息

- Repo: `https://github.com/00660/hme-manager-encrypted-updates`
- Manifest: `https://github.com/00660/hme-manager-encrypted-updates/raw/refs/heads/main/update_manifest.json`
- Install Script: `https://github.com/00660/hme-manager-encrypted-updates/raw/refs/heads/main/install.sh`
- Branch: `main`
- Manifest Name: `update_manifest.json`
