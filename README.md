# xray-release-public

这是现在在用的无前端包仓。

先看现在保留的 4 个仓：

| 仓库 | 前端 | Mihomo | 类型 | 现在用途 |
| --- | --- | --- | --- | --- |
| `xray-frontend-source` | 有 | 没有 | 源码仓 | 改带前端代码 |
| `xray-frontend-package-public` | 有 | 没有 | 包仓 | 下带前端安装包 |
| `xray-headless-source` | 没有 | 有 | 源码仓 | 改无前端代码 |
| `xray-release-public` | 没有 | 有 | 包仓 | 下无前端安装包 |

## 先记住这件事

- 现在真正要看的只有这 4 个仓
- 这个仓是“无前端 + 包仓”
- 无前端包里已经带上 Mihomo 相关辅助能力

## 这个仓里是什么

- 无前端版本安装包
- 这里不放源码
- 对应源码仓是 `xray-headless-source`

## 什么时候来这里

- 你要下载无前端版本
- 你只想拿安装包和校验文件
- 你要用带 Mihomo 辅助能力的 headless 线

## 什么时候不要来这里

- 你要改源码
- 你要改网页面板
- 你要带前端版本

## 当前文件

- 安装包：`xray-backend-release.tar.gz`
- 校验文件：`SHA256SUMS.txt`
- 对应源码仓：[`huotian420-cyber/xray-headless-source`](https://github.com/huotian420-cyber/xray-headless-source)

## 下载

```bash
curl -fL --progress-bar -o xray-backend-release.tar.gz https://raw.githubusercontent.com/huotian420-cyber/xray-release-public/main/xray-backend-release.tar.gz
```

```bash
curl -fL --progress-bar -o SHA256SUMS.txt https://raw.githubusercontent.com/huotian420-cyber/xray-release-public/main/SHA256SUMS.txt
sha256sum -c SHA256SUMS.txt
```

```bash
sudo bash -c 'set -e; apt-get update -y; apt-get install -y curl tar; workdir=$(mktemp -d); cd "$workdir"; curl -fL --progress-bar -o xray-backend-release.tar.gz https://raw.githubusercontent.com/huotian420-cyber/xray-release-public/main/xray-backend-release.tar.gz; tar -xzf xray-backend-release.tar.gz; chmod +x install.sh; ./install.sh'
```
