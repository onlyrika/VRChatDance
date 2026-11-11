# 跳舞房助手 · 发布仓库

这个仓库只用来存 **跳舞房助手（C++/Qt6 版）** 的更新包和版本清单，不存源码。

## 程序端怎么用

程序里的「检查更新」按顺序试两个源，第一个成功的为准：

1. **GitHub**（主）：
   - 清单 https://github.com/onlyrika/VRChatDance/releases/latest/download/version-qt.json
   - 更新包 https://github.com/onlyrika/VRChatDance/releases/latest/download/vrclqt-<版本>.zip
2. **云服**（回退）：https://110.42.220.245/version-qt.json

`releases/latest/download/` 永远指向最新一次 release，发新版只建新 tag，上面两个 URL 不用改。

## 清单格式

``json
{
  "version": "1.6.4",
  "fileName": "vrclqt-1.6.4.zip",
  "size": 12619172,
  "sha256": "整包 sha256（小写 hex）",
  "notes": "更新说明",
  "publishedAt": "2026-11-11T23:11:20.132817+08:00"
}
``

## 发版

在工程目录跑：

``bat
tools\发布上传.ps1
``

会用 GitHub API 建 release（tag = `v<版本>`）、上传清单和 zip，再用公开链接回验。