<div align="center">
  <img src="https://raw.githubusercontent.com/juejin-sync/juejin-sync/master/assets/logo-128.png" width="96" height="96" alt="掘金同步助手 Logo">
  <h1>掘金同步助手 · Juejin Sync</h1>
  <p><b>将掘金文章同步到多个内容平台的草稿箱。</b></p>
  <p>
    <a href="https://github.com/juejin-sync/juejin-sync/releases/latest">
      <img src="https://img.shields.io/github/v/release/juejin-sync/juejin-sync?display_name=tag&sort=semver&label=release" alt="Latest release">
    </a>
    <a href="https://github.com/juejin-sync/juejin-sync/actions/workflows/ci.yml">
      <img src="https://github.com/juejin-sync/juejin-sync/actions/workflows/ci.yml/badge.svg" alt="CI status">
    </a>
    <a href="https://github.com/juejin-sync/juejin-sync/stargazers">
      <img src="https://img.shields.io/github/stars/juejin-sync/juejin-sync?style=flat&label=stars" alt="GitHub stars">
    </a>
    <a href="https://github.com/juejin-sync/juejin-sync/blob/master/LICENSE">
      <img src="https://img.shields.io/badge/license-MIT-2f855a" alt="MIT License">
    </a>
  </p>
  <p>
    <a href="https://github.com/juejin-sync/juejin-sync">查看源码</a> ·
    <a href="https://github.com/juejin-sync/juejin-sync/releases/latest">下载扩展</a> ·
    <a href="https://juejin-sync.github.io/juejin-sync/status.html">运行状态</a> ·
    <a href="https://artferry.vercel.app">官方网站</a>
  </p>
</div>

## 项目简介

掘金同步助手是一款开源的 Chrome Manifest V3 浏览器扩展。它读取用户主动选择的掘金文章或编辑器草稿，处理正文与图片，并同步到已登录内容平台的草稿箱。

## 核心项目

| 仓库 | 说明 |
| --- | --- |
| [`juejin-sync`](https://github.com/juejin-sync/juejin-sync) | 浏览器扩展源码、Release 安装包、问题反馈与开发文档 |

## 它能做什么

- 从掘金编辑器、创作者中心或个人文章页主动发起同步
- 多个平台独立执行并记录结果，单个平台失败不影响其他平台
- 转换正文格式并按平台要求转存图片、封面和摘要
- 更新草稿前检查远端状态，避免误覆盖已经公开发布的内容
- 所有转换均在浏览器扩展内完成，不托管账号密码和文章正文

## 已验证支持平台

| 平台 | 当前能力 |
| --- | --- |
| 掘金 | 读取编辑器草稿及已发布文章，识别发布成功状态 |
| CSDN | 创建和更新草稿，转存正文图片、封面与摘要 |
| 微信公众号 | 创建和更新草稿，处理微信专用排版、正文图与封面 |
| 博客园 | 创建和更新随笔草稿，转存正文图片与题图 |

## 设计原则

- **用户主动触发**：只在明确勾选平台或点击同步按钮后读取文章并执行任务
- **数据不离开设备**：没有中间服务器，不上传账号密码，不申请 Chrome `cookies` 权限
- **草稿优先**：只写入目标平台草稿箱，公开发布前始终由用户检查确认
- **失败可诊断**：平台任务独立记录状态，提供明确的处理提示与安全重试入口

## 快速开始

推荐从 [Releases](https://github.com/juejin-sync/juejin-sync/releases/latest) 下载最新安装包，解压后在 `chrome://extensions/` 中开启开发者模式并选择“加载已解压的扩展程序”。

从源码运行：

```bash
git clone https://github.com/juejin-sync/juejin-sync.git
cd juejin-sync
npm ci
npm run check
npm test
npm run build
```

## 参与项目

欢迎通过 [Issues](https://github.com/juejin-sync/juejin-sync/issues) 提交问题与建议，也欢迎参与代码贡献。项目采用 [MIT License](https://github.com/juejin-sync/juejin-sync/blob/master/LICENSE) 开源。

> 掘金同步助手是社区开源项目，与掘金官方不存在隶属或授权关系。
