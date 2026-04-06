# xray-release-public

这是无前端的包仓。

先看这个表：

| 仓库 | 前端网页面板 | Mihomo | 类型 |
| --- | --- | --- | --- |
| `xray-frontend-source` | 有 | 没有 | 源码仓 |
| `xray-frontend-package-public` | 有 | 没有 | 包仓 |
| `xray-headless-source` | 没有 | 有 | 源码仓 |
| `xray-release-public` | 没有 | 有 | 包仓 |

## 这个仓是什么

- 无前端
- 带 Mihomo 辅助能力
- 这是包仓，不是源码仓
- 这里放的是 headless 版本安装包

## 这里说的“带 Mihomo”是什么意思

- 不是用 Mihomo 跑服务端
- 服务端核心还是 `Xray`
- 这里的 Mihomo 指：
  - 安装器会尝试装 `mihomo`
  - 可以给客户端导出 `Mihomo / Clash YAML`
  - 有统一订阅 URL
  - 有证书时订阅会直接走 `HTTPS`

## 你什么时候来这个仓

- 你要下载无前端版本
- 你只关心安装包和校验文件
- 你要带 Mihomo 辅助能力的 headless 线

## 你不要来这个仓的情况

- 你要改源码
- 你要改网页面板
- 你要带前端版本

## 当前文件

- 安装包：`xray-backend-release.tar.gz`
- 校验文件：`SHA256SUMS.txt`
- 对应源码仓：[`huotian420-cyber/xray-headless-source`](https://github.com/huotian420-cyber/xray-headless-source)

## 下载

最新版本：

```bash
curl -fL --progress-bar -o xray-backend-release.tar.gz https://raw.githubusercontent.com/huotian420-cyber/xray-release-public/main/xray-backend-release.tar.gz
```

校验：

```bash
curl -fL --progress-bar -o SHA256SUMS.txt https://raw.githubusercontent.com/huotian420-cyber/xray-release-public/main/SHA256SUMS.txt
sha256sum -c SHA256SUMS.txt
```

一键安装：

```bash
sudo bash -c 'set -e; apt-get update -y; apt-get install -y curl tar; workdir=$(mktemp -d); cd "$workdir"; curl -fL --progress-bar -o xray-backend-release.tar.gz https://raw.githubusercontent.com/huotian420-cyber/xray-release-public/main/xray-backend-release.tar.gz; tar -xzf xray-backend-release.tar.gz; chmod +x install.sh; ./install.sh'
```

## 4 个仓怎么选

- 你要改带前端代码：去 `xray-frontend-source`
- 你要下载带前端包：去 `xray-frontend-package-public`
- 你要改无前端代码：去 `xray-headless-source`
- 你要下载无前端包：去 `xray-release-public`
