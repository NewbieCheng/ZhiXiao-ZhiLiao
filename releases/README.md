# 安装包目录

本目录存放从 monorepo 打包同步的安装包，**默认不提交到 Git**（见上级 `.gitignore`）。

## 当前文件

| 文件 | 产品 | 版本 |
|------|------|------|
| `ZhiLiao-5.2.0-Setup.exe` | 知聊 | 5.2.0 |
| `PrivateKings-2.0preview-win-x64.exe` | 知销 | 2.0preview |

## 同步命令

在 WeFlow 源码仓库根目录：

```bash
node scripts/sync-zhixiao-zhiliao-release.cjs
```

## 上传到 GitHub Releases

1. 在本仓库创建 Release，Tag 建议：`zhiliao-v5.2.0` / `zhixiao-v2.0preview` 或统一 `v2026.06.22`。
2. 将上表两个 `.exe` 作为附件上传。
3. 在 Release 说明中链接 `docs/知聊使用指南.md` 与 `docs/知销使用指南.md`。
