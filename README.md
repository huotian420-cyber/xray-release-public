# xray-release-public

无前端 / CLI-first 版本的公开安装包仓。这里只放可下载的发布包和校验文件，不放源码。

## 四个仓库分工

| 仓库 | 类型 | 前端 | Mihomo | 用途 |
| --- | --- | --- | --- | --- |
| `xray-frontend-source` | 源码仓 | 有 | 无 | 开发带 Web 面板版本 |
| `xray-frontend-package-public` | 包仓 | 有 | 无 | 下载带 Web 面板安装包 |
| `xray-headless-source` | 源码仓 | 无 | 有 | 开发无前端 / CLI-first 版本 |
| `xray-release-public` | 包仓 | 无 | 有 | 下载无前端安装包 |

## 本仓定位

- 公开包仓，面向安装和升级。
- 对应源码仓：`huotian420-cyber/xray-headless-source`。
- 发布包包含后端二进制和 `install.sh`。
- 不包含 Web 面板、不包含源码、不包含带前端版本、不包含客户端安装包。

## 当前文件

- `xray-backend-release.tar.gz`：无前端安装包。
- `SHA256SUMS.txt`：安装包 SHA256 校验文件。

## 当前关键能力

- CLI-first，通过 `xy` 管理。
- 支持加密 V2Ray 订阅 URL 和 Mihomo / Clash YAML。
- Mihomo YAML 是可直接运行的完整配置，支持新版 Mihomo / Clash Meta 的 XHTTP `xhttp-opts`。
- 支持哪吒 Agent 官方安装参数导入。
- 支持 Cloudflare 优选域名订阅导出和每日自动抓取。

## 下载并校验

```bash
curl -fL --progress-bar -o xray-backend-release.tar.gz https://raw.githubusercontent.com/huotian420-cyber/xray-release-public/main/xray-backend-release.tar.gz
curl -fL --progress-bar -o SHA256SUMS.txt https://raw.githubusercontent.com/huotian420-cyber/xray-release-public/main/SHA256SUMS.txt
sha256sum -c SHA256SUMS.txt
```

## 全新安装 / 覆盖更新

```bash
sudo bash -c 'set -e; apt-get update -y; apt-get install -y curl tar coreutils; workdir=$(mktemp -d); cd "$workdir"; curl -fL --progress-bar -o xray-backend-release.tar.gz https://raw.githubusercontent.com/huotian420-cyber/xray-release-public/main/xray-backend-release.tar.gz; curl -fL --progress-bar -o SHA256SUMS.txt https://raw.githubusercontent.com/huotian420-cyber/xray-release-public/main/SHA256SUMS.txt; sha256sum -c SHA256SUMS.txt; tar -xzf xray-backend-release.tar.gz; chmod +x install.sh; ./install.sh'
```

## 从源码仓同步

在 `xray-headless-source` 工作区执行：

```bash
cd backend
PUBLIC_RELEASE_DIR=../release_public_stable_work bash package-release.sh
```

脚本只应同步：

- `xray-backend-release.tar.gz`
- `SHA256SUMS.txt`

## 维护规则

- 不提交源码目录。
- 不提交 `.codex-*` 临时文件。
- 不把带前端包放进本仓。
- 每次更新包后同时更新 `SHA256SUMS.txt`。
