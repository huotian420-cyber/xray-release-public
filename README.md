# xray-release-public

这是无前端安装包的公开发布仓。

## 仓库角色

- 可见性：`public`
- 内容：当前最新无前端安装包、校验文件、Release 历史版本
- 用途：直接下载 headless 安装包

## 不要拿它做什么

- 不要把它当源码仓
- 不要把它当带前端安装包仓

## 当前发布

- 包名：`xray-backend-release.tar.gz`
- 校验：`SHA256SUMS.txt`
- 对应源码仓：[`huotian420-cyber/xray-headless-source`](https://github.com/huotian420-cyber/xray-headless-source)
- 当前对应源码提交：`7cab790` `Fix headless TLS XHTTP ALPN defaults`
- 当前固定版本：`v2026.04.01-headless-direct-3`

## Tag 规则

- 无前端公开包统一使用：
  - `vYYYY.MM.DD-headless-direct-N`
- 例子：
  - `v2026.04.01-headless-direct-1`
- 含义：
  - `YYYY.MM.DD`：发布日期
  - `headless`：无前端安装包
  - `direct`：当前这条公开直发稳定线
  - `N`：当天递增版本号

## 当前版本说明

- 这是稳定线的无前端包
- 默认不带网页面板
- `TLS / Reality` 由 `Xray` 直接监听
- 安装脚本已对齐官方正式版 `Xray-core v26.3.27`
- 已移除 SSH 敲门，默认 SSH `22` 保持开放，可在管理菜单里切换到自定义端口
- 已按当前官方行为补齐 `XHTTP / gRPC / ALPN(h3/h2/http/1.1)` 兼容

## 下载

Ubuntu 一键安装最新版本：

```bash
sudo bash -c 'set -e; apt-get update -y; apt-get install -y curl tar; workdir=$(mktemp -d); cd "$workdir"; curl -fL --progress-bar -o xray-backend-release.tar.gz https://raw.githubusercontent.com/huotian420-cyber/xray-release-public/main/xray-backend-release.tar.gz; tar -xzf xray-backend-release.tar.gz; chmod +x install.sh; ./install.sh'
```

Ubuntu 一键安装固定版本：

```bash
sudo bash -c 'set -e; apt-get update -y; apt-get install -y curl tar; workdir=$(mktemp -d); cd "$workdir"; curl -fL --progress-bar -o xray-backend-release.tar.gz https://raw.githubusercontent.com/huotian420-cyber/xray-release-public/v2026.04.01-headless-direct-3/xray-backend-release.tar.gz; tar -xzf xray-backend-release.tar.gz; chmod +x install.sh; ./install.sh'
```

最新版本：

```bash
curl -fL --progress-bar -o xray-backend-release.tar.gz https://raw.githubusercontent.com/huotian420-cyber/xray-release-public/main/xray-backend-release.tar.gz
```

固定版本：

```bash
curl -fL --progress-bar -o xray-backend-release.tar.gz https://raw.githubusercontent.com/huotian420-cyber/xray-release-public/v2026.04.01-headless-direct-3/xray-backend-release.tar.gz
```

校验：

```bash
curl -fL --progress-bar -o SHA256SUMS.txt https://raw.githubusercontent.com/huotian420-cyber/xray-release-public/main/SHA256SUMS.txt
sha256sum -c SHA256SUMS.txt
```

## 4 个仓怎么分

- 带前端私有源码：[`huotian420-cyber/xray-`](https://github.com/huotian420-cyber/xray-)
- 无前端私有源码：[`huotian420-cyber/xray-headless-source`](https://github.com/huotian420-cyber/xray-headless-source)
- 带前端公开安装包：[`huotian420-cyber/xray-frontend-release-public`](https://github.com/huotian420-cyber/xray-frontend-release-public)
- 无前端公开安装包：[`huotian420-cyber/xray-release-public`](https://github.com/huotian420-cyber/xray-release-public)

## 如果你的目标不是下载包

- 要改带前端代码：去 `xray-`
- 要改无前端源码：去 `xray-headless-source`
- 要下带前端包：去 `xray-frontend-release-public`
