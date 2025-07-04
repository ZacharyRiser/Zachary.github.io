---
title: Windows安装部署Gemini Cli
date: 2025-07-04 16:06:23
tags:
---

# Gemini CLI 安装步骤

## 步骤一：安装 Node.js
- 访问 [Node.js 官网](https://nodejs.org/) 下载安装包
- 运行安装程序（默认设置即可）
- 验证安装：
  ```bash
  node -v
  ```

## 步骤二：安装 Gemini CLI
- 使用全局安装命令：
  ```bash
  npm install -g @google/gemini-cli
  ```
- 验证安装：
  ```bash
  gemini --version
  ```

## 步骤三：身份验证
- 运行登录命令：
  ```bash
  gemini login
  ```
- 系统会自动打开浏览器
- 使用 Google 账号登录并授权
- 终端显示 "Login successful!" 即完成

最终显示如图所示：

![image](https://github.com/user-attachments/assets/293aee2d-9adc-4512-8ab7-2345a436c8f3)

## troubleshooting

### 1. Git 安装与权限问题

#### 错误现象：Git 命令未找到
```bash
npm ERR! code ENOENT 
npm ERR! syscall spawn git
```

**解决方案**：

1. 下载安装 Git：
   - [点击下载 Git for Windows](https://git-scm.com/download/win)
   - 安装时勾选：
     - "Use Git from the Windows Command Prompt"  
     - "Enable symbolic links"

2. 验证安装：
```bash
git --version
```

3. 检查环境变量 Path 是否包含：
```
C:\Program Files\Git\cmd
C:\Program Files\Git\bin
```

### 2. Gemini CLI 认证问题

#### 错误现象：认证失败
```bash
Error: Authentication expired
或
Waiting for authentication...
```

**解决方案**：

1. 清除旧凭证：
```bash
gemini logout
```

2. 重新登录：
```bash
gemini login
```

3. 如浏览器未自动打开：
```bash
gemini login --no-browser
```
- 手动访问终端显示的链接
- 粘贴返回的授权码

### 问题反馈
如果遇到问题，请提供以下信息以便进一步排查：
```bash
gemini --version
node -v  
git --version
```
### 3. 权限问题

#### 错误现象：文件安装在系统文件system里面时会导致权限问题

**解决方案**： 
  避免在system文件夹里安装东西

```
