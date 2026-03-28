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
- `f1229d7` `Refresh headless stable release package`

当前根目录同步的公开包：
- 基于稳定线 `main` 的最新无前端安装包
- 安装脚本已对齐官方正式版 `Xray-core v26.3.27`
- 已包含 `Reality x25519` 新输出兼容、`XHTTP mode` 选择和 `Reality shortIds` 归一化

推荐下载命令：

```bash
curl -fL --progress-bar -o xray-backend-release.tar.gz https://raw.githubusercontent.com/huotian420-cyber/xray-release-public/main/xray-backend-release.tar.gz
```

校验命令：

```bash
curl -fL --progress-bar -o SHA256SUMS.txt https://raw.githubusercontent.com/huotian420-cyber/xray-release-public/main/SHA256SUMS.txt
sha256sum -c SHA256SUMS.txt
```

和另外 3 个仓的关系：
- 带前端私有完整源码仓：
  - [huotian420-cyber/xray-](https://github.com/huotian420-cyber/xray-)
- 无前端私有源码仓：
  - [huotian420-cyber/xray-headless-source](https://github.com/huotian420-cyber/xray-headless-source)
- 公开带前端安装包仓：
  - [huotian420-cyber/xray-frontend-release-public](https://github.com/huotian420-cyber/xray-frontend-release-public)

说明：
- Release 页面可保留历史无前端版本
- 仓库根目录只保留当前最新的无前端包
- 如果你要带前端安装包，不要下这个仓，去 `xray-frontend-release-public`
