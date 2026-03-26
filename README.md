# xray-release-public

这是 **公开的无前端安装包仓库**。

你需要这样理解它：
- 这里只放 **无前端 / headless** 版本安装包
- 仓库根目录始终保留当前最新的无前端包
- Release 页面保留历史版本的无前端包

它 **不是**：
- 带前端公开安装包仓
- 私有源码仓

当前文件：
- `xray-backend-release.tar.gz`
- `SHA256SUMS.txt`

对应私有源码提交：
- `ad6a35a` `Add VLESS Encryption support to headless nodes`

当前根目录同步的公开包：
- `v2026.03.26-headless-direct-2`

推荐下载命令：

```bash
curl -fL --progress-bar -o xray-backend-release.tar.gz https://github.com/huotian420-cyber/xray-release-public/releases/download/v2026.03.26-headless-direct-2/xray-backend-release.tar.gz
```

仓库根目录直链：

```bash
curl -fL --progress-bar -o xray-backend-release.tar.gz https://raw.githubusercontent.com/huotian420-cyber/xray-release-public/main/xray-backend-release.tar.gz
```

和另外 3 个仓的关系：
- 带前端私有完整源码仓：
  - [huotian420-cyber/xray-](https://github.com/huotian420-cyber/xray-)
- 无前端私有源码仓：
  - [huotian420-cyber/xray-headless-source](https://github.com/huotian420-cyber/xray-headless-source)
- 公开带前端安装包仓：
  - [huotian420-cyber/xray-frontend-release-public](https://github.com/huotian420-cyber/xray-frontend-release-public)

说明：
- Release 页面保留历史无前端版本
- 仓库根目录只保留当前最新的无前端包
- 如果你要带前端安装包，不要下这个仓，去 `xray-frontend-release-public`
