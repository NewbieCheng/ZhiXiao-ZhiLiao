# 知聊 · 知销（ZhiLiao & ZhiXiao）

> 用户下载与使用文档仓库 · 不含源码  
> 源码开发仓库：[NewbieCheng/WeFlow](https://github.com/NewbieCheng/WeFlow)

本仓库提供 **知聊**（微信本地聊天查看 / 导出 / 分析）与 **知销**（AI 销售回复助手）的 Windows 安装包与使用教程。

## 最新版本

| 产品 | 版本 | 安装包 | 说明 |
|------|------|--------|------|
| **知聊** | 5.2.0 | [ZhiLiao-5.2.0-Setup.exe](releases/ZhiLiao-5.2.0-Setup.exe) | 微信 4.0+ 本地读库、导出、SOP、HTTP API |
| **知销** | 2.0preview | [PrivateKings-2.0preview-win-x64.exe](releases/PrivateKings-2.0preview-win-x64.exe) | AI 回复建议、知识库、记忆、微信自动化 |

> 安装包体积较大，若 GitHub 网页无法直接下载，请在本仓库 **Releases** 页获取，或使用本地 `releases/` 目录中的文件。

## 使用教程

| 文档 | 内容 |
|------|------|
| [知聊使用指南](docs/知聊使用指南.md) | 安装、连库、聊天/导出/SOP/本地 API |
| [知销使用指南](docs/知销使用指南.md) | 安装、授权、连 WeFlow、工作台 / 知识库 / 自动化 |
| [联调说明](docs/联调说明.md) | 知聊 + 知销 同时运行时的推荐步骤 |

## 系统要求

| 项 | 知聊 | 知销 |
|----|------|------|
| 系统 | Windows 10/11 x64（安装包）；亦支持 macOS / Linux 开发版 | Windows 10/11 x64 |
| 微信 | PC 微信 **4.0+** | 读个人聊天需 **知聊已开 HTTP API**；发朋友圈 / 自动回复需本机微信 |
| 数据目录 | `文档\WeFlow\` | `文档\PrivateKings\` |

## 推荐安装顺序（联用）

1. 安装并启动 **知聊**，完成微信数据库连接。
2. 知聊 → **设置 → Agent 连接**，启用本地 HTTP API（默认端口 `5031`），设置 Token。
3. 安装并启动 **知销** → **设置 → 微信数据**，填写 API 地址与 Token，测试连接。
4. 在知销 **会话 / 工作台** 中使用 AI 回复建议。

## 从源码重新打包

在 monorepo 根目录（WeFlow 源码仓库）执行：

```bash
npm run build                  # 知聊安装包 → release/
npm run private-kings:build    # 知销安装包 → release-private-kings/
node scripts/sync-zhixiao-zhiliao-release.cjs   # 同步到本仓库 releases/
```

## 仓库结构

```
release-zhixiao-zhiliao/
├── README.md
├── VERSIONS.json
├── docs/
│   ├── 知聊使用指南.md
│   ├── 知销使用指南.md
│   └── 联调说明.md
└── releases/
    ├── README.md
    ├── ZhiLiao-5.2.0-Setup.exe
    └── PrivateKings-2.0preview-win-x64.exe
```

## 反馈

问题与功能建议请在对应源码仓库提交 Issue，或联系分发渠道维护者。
