# scoopApps

[![Tests](https://github.com/Wzzz-10086/scoopApps/actions/workflows/ci.yml/badge.svg)](https://github.com/Wzzz-10086/scoopApps/actions/workflows/ci.yml)
[![Excavator](https://github.com/Wzzz-10086/scoopApps/actions/workflows/excavator.yml/badge.svg)](https://github.com/Wzzz-10086/scoopApps/actions/workflows/excavator.yml)

个人维护的 [Scoop](https://scoop.sh) bucket，用于收录未进入官方 bucket、但日常使用需要的 Windows 应用。

## 添加 Bucket

```powershell
scoop bucket add scoopApps https://github.com/Wzzz-10086/scoopApps
```

确认是否添加成功：

```powershell
scoop bucket list
```

## 安装应用

当前收录：

| 应用 | 描述 | 安装命令 |
| --- | --- | --- |
| PixPin | 截图、录屏、OCR - 一款快速灵活的工具 | `scoop install scoopApps/pixpin` |
| Recordly | 制作精致、专业级的屏幕录制视频 | `scoop install scoopApps/recordly` |
| CodexPlusPlus | 一个CodexApp的增强工具，努力让Codex变得更好用更舒服 | `scoop install scoopApps/codexplusplus` |
| FluxDown | 跨平台多线程下载器，多协议支持，零广告零追踪 | `scoop install scoopApps/fluxdown` |
| OpenChamber | OpenCode 的现代化富交互界面客户端 | `scoop install scoopApps/openchamber` |

## 更新

更新 Scoop 与所有 bucket：

```powershell
scoop update
```

更新已安装应用：

```powershell
scoop update *
```

## 自动更新

本仓库使用 GitHub Actions 的 `Excavator` 检查 manifest 更新。

- 支持手动触发
- 定时任务：每 4 小时运行一次（与官方 Scoop Bucket 频率保持一致）

## 维护说明

新增 manifest 放在 `bucket/<app-name>.json`。

提交前建议至少执行：

```powershell
jq . bucket/<app-name>.json
```

如本机 Scoop 测试依赖完整，也可以执行：

```powershell
powershell -NoProfile -ExecutionPolicy Bypass -File .\Scoop-Bucket.Tests.ps1
```
