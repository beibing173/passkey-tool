# Passkey 设备配置工具 (Device Commissioning Tool)

这是一个基于 Web 的设备配置工具，专门用于配置和初始化 Passkey/FIDO2 硬件设备。该项目提取自 [passkey.phphy.com](https://passkey.phphy.com/)，旨在提供一个独立且可自定义的设备管理界面。

## 🚀 功能特性

- **身份信息配置 (Identity)**: 自定义产品名称，支持多种 USB VID:PID 预设（如 Nitrokey, Yubikey 等）。
- **硬件参数调整 (Hardware)**: 
  - 支持多种 LED 驱动（PICO, WS2812, CYW43 等）。
  - 可调节 LED GPIO 引脚、亮度和工作模式（常亮、调光等）。
  - 设置按键超时时间。
- **算法支持 (ECC Curves)**: 支持 Secp256r1, Secp256k1 和 Ed25519 曲线。
- **安全启动 (Secure Boot)**: 提供签名校验和硬件锁定功能。
- **多种写入方式**: 支持通过 WebUSB 和 WebAuthn 进行设备连接与数据写入。

## 🛠️ 部署指南

该项目是一个纯前端的单页面应用 (SPA)，可以部署在任何支持静态文件托管的平台上。

### 1. GitHub Pages 部署 (推荐)
1. 将此仓库推送到 GitHub。
2. 进入仓库的 **Settings > Pages**。
3. 在 **Build and deployment** 部分，选择 `main` 分支和 `/(root)` 目录。
4. 点击 **Save**，稍等片刻即可通过 `https://<your-username>.github.io/passkey-tool/` 访问。

### 2. 本地运行
由于项目使用了 WebUSB 和 WebAuthn API，浏览器出于安全考虑要求必须在 **HTTPS** 环境或 **localhost** 下运行。
```bash
# 使用 Python 快速启动本地服务
python3 -m http.server 8000
```
然后在浏览器访问 `http://localhost:8000`。

## ⚠️ 重要说明

- **HTTPS 限制**: WebUSB 和 WebAuthn 功能在非加密的 HTTP 环境下（除 localhost 外）将被浏览器禁用。
- **硬件兼容性**: 该工具通过 Web 标准 API 与硬件交互，请确保您的浏览器（推荐 Chrome/Edge）支持相关特性。

## 📄 许可

本项目内容提取自公开资源，仅供学习和研究使用。
