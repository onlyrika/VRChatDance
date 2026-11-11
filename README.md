# 跳舞房助手 · 发布仓库

这个仓库只用来存 **跳舞房助手（C++/Qt6 版）** 的更新包和版本清单，不存源码。

## 唯一的更新源

程序的「检查更新」只访问 GitHub：

- 清单 https://github.com/onlyrika/VRChatDance/releases/latest/download/version-qt.json
- 更新包 https://github.com/onlyrika/VRChatDance/releases/latest/download/vrclqt-&lt;版本&gt;.zip

`releases/latest/download/` 永远指向最新一次 release，发新版只建新 tag，上面两个 URL 不用改。
没有任何回退地址、没有第三方服务器。

## 清单格式

```json
{
  "version": "1.7.0",
  "fileName": "vrclqt-1.7.0.zip",
  "size": 12623000,
  "sha256": "整包 sha256（小写 hex）",
  "notes": "更新说明",
  "publishedAt": "2026-11-12T00:30:00.000000+08:00"
}
```

程序端会核对 `version`（点分逐段比较）、`size`（字节数）和 `sha256`（整包哈希），三者都对才安装。

## 发版

在工程目录跑：

```bat
tools\发布上传.ps1
```

会用 GitHub API 建 release（tag = `v<版本>`）、上传清单和 zip，再用公开链接回验。需要 `GITHUB_TOKEN`。
