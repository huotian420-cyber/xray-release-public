# xray-release-public

公开安装包仓库，仓库根目录始终保留当前可直接下载的最新版安装包。

当前文件：
- `xray-backend-release.tar.gz`
- `SHA256SUMS.txt`

对应私有源码提交：
- `7c5cecb` `Refresh headless release package`

当前根目录同步的公开包：
- `v2026.03.21-headless-direct-1`

推荐下载命令：

```bash
curl -fL --progress-bar -o xray-backend-release.tar.gz https://github.com/huotian420-cyber/xray-release-public/releases/download/v2026.03.21-headless-direct-1/xray-backend-release.tar.gz
```

仓库根目录直链：

```bash
curl -fL --progress-bar -o xray-backend-release.tar.gz https://raw.githubusercontent.com/huotian420-cyber/xray-release-public/main/xray-backend-release.tar.gz
```

说明：
- Release 页面始终保留按版本号归档的安装包
- 仓库根目录只保留当前最新的可直接下载包
