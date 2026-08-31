# xray-release-public

无前端 / CLI-first 版本的公开安装包仓。这里只放发布包和校验文件，不放源码。

## 本仓定位

- 对应源码仓：`huotian420-cyber/xray-headless-source`
- 不包含 Web 前端、管理员登录、公网管理 API 或客户端辅助内核。
- 不提供 Mihomo/Clash YAML 或 AES 订阅封装。
- 通过 `xy` 管理节点、证书、订阅、防火墙和系统运维。

## 当前文件

- `xray-backend-release.tar.gz`：Linux AMD64/ARM64 安装包。
- `SHA256SUMS.txt`：安装包 SHA256 校验文件。

## 下载并校验

```bash
curl -fL --progress-bar -o xray-backend-release.tar.gz https://raw.githubusercontent.com/huotian420-cyber/xray-release-public/main/xray-backend-release.tar.gz
curl -fL --progress-bar -o SHA256SUMS.txt https://raw.githubusercontent.com/huotian420-cyber/xray-release-public/main/SHA256SUMS.txt
sha256sum -c SHA256SUMS.txt
```

## 安装或更新

```bash
tar -xzf xray-backend-release.tar.gz
chmod +x install.sh
./install.sh
```

安装器会自动识别 Ubuntu、Debian 和 Red Hat 系发行版；Debian/Ubuntu 缺少时会安装 `ufw` 与 `fail2ban`。HY2 默认关闭，不会默认开放 UDP 跳跃端口。

清空旧节点、订阅 token 和流量状态后重装：

```bash
XRAY_BACKEND_PURGE=1 ./install.sh
```

## 订阅和服务

- `xy` 生成标准 VLESS/Hysteria2 链接和 V2Ray Base64 订阅。
- 订阅服务使用 HTTPS；证书缺失或无效时不会降级为明文 HTTP。
- Xray Stats API 仅监听 `127.0.0.1:10085`。
- HY2 只有在通过 `xy` 显式创建/启用后才会使用 UDP 端口范围。

## 从源码仓同步

在源码仓的 `backend/` 目录执行：

```bash
PUBLIC_RELEASE_DIR=../release_public_stable_work bash package-release.sh
```

脚本只同步 `xray-backend-release.tar.gz` 和 `SHA256SUMS.txt`。

## 维护规则

- 不提交源码目录、临时日志或本地调试产物。
- 每次更新发布包后同时更新 `SHA256SUMS.txt`。
- 包仓与源码仓分开提交、分开推送。
