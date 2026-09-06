<div align="center">

<img src="Resources/icon.png" width="160" alt="ShotX">

# ShotX（中文版）

<img width="300" height="500" alt="ShotX 界面展示" src="https://github.com/user-attachments/assets/290b64e7-7e0d-41d7-9d34-a2d7953e8643" />

**专为 macOS 菜单栏设计的现代化截图与录屏工具。**  
支持区域截图、带摄像头画中画的屏幕录制、GIF 导出、即时标注、屏幕取色、OCR 文字提取以及可搜索的历史记录 —— 全程无需离开键盘。

![macOS](https://img.shields.io/badge/macOS-13%2B-007AFF?style=flat&logo=apple&logoColor=white)
![Swift](https://img.shields.io/badge/Swift-5.9-F05138?style=flat&logo=swift&logoColor=white)
![Menu bar](https://img.shields.io/badge/菜单栏常驻-1F2937?style=flat)
[![Latest release](https://img.shields.io/github/v/release/aimen08/shotx?style=flat&color=22C55E)](https://github.com/aimen08/shotx/releases/latest)

[功能特性](#功能特性) · [默认快捷键](#默认快捷键) · [从源码构建](#从源码构建) · [开发计划](#开发计划)

</div>

---

## 功能特性

- **屏幕截图**：支持选区截图、窗口截图、全屏截图、截取上一区域；支持定时延时截图（3 / 5 / 10 秒）；支持从剪贴板或本地文件打开图像。
- **屏幕录制**：基于 ScreenCaptureKit 录制 H.264 MP4 视频或高清 GIF（12 fps，720 px），支持麦克风录音、系统内部声音捕获及鼠标点击高亮波纹。
- **摄像头画中画**：录屏时在录制区域左下角显示圆形摄像头画面；预览期间支持拖拽定位和调整尺寸，录制时自动嵌入画面中。
- **即时标注**：提供箭头、矩形框、文字、步骤序号等标注工具；内置 8 色调色盘，一键快捷键复制或保存。
- **文字识别 (OCR)**：框选区域即可通过 Apple Vision 离线高精度识别文字（已加入中文字符识别支持），自动复制到剪贴板。
- **历史记录**：本地保存最近 100 次截图记录，支持缩略图预览与搜索管理。
- **屏幕取色**：原生放大镜拾色器，拾取后十六进制颜色代码（HEX）自动写入剪贴板。
- **屏幕贴图与拖拽**：支持将截图以浮动窗口固定在屏幕上，支持直接拖拽图片到其他应用。
- **可自定义全局快捷键**：即改即生效，无需重启应用。

---

## 默认快捷键

| 操作 | 快捷键 |
|------|--------|
| 截取区域 | `⌥X` |
| 截取全屏 | `⌥⇧X` |
| 提取文字 (OCR) | `⌥⇧T` |
| 屏幕取色 | `⌥⇧C` |
| 停止录屏 | `⌘.` |
| 从剪贴板打开 | `⇧⌘V` |
| 设置 | `⌘,` |
| 退出 | `⌘Q` |

所有全局快捷键均可在 **设置 → 快捷键** 中自定义修改。

---

## 系统要求

- 需要 **macOS 13.0** 或更高版本。

---

## 从源码构建

需要环境：Swift 5.9 + macOS 13 SDK（Xcode 15+）。

```bash
git clone https://github.com/xavianzhang/shotx-Chinese.git
cd shotx-Chinese

swift run                             # 开发调试运行
./Scripts/build-app.sh                # 打包生成 ShotX.app
./Scripts/make-dmg.sh                 # 打包生成 DMG 安装包
./Scripts/release.sh                  # 编译构建 + 打标签 + 发布 GitHub Release
```

**保持权限稳定（推荐）**：  
在 macOS“钥匙串访问”中创建一个自签名的 *代码签名（Code Signing）* 证书，并将其名称保存到根目录下的 `.signing-identity` 文件中。后续构建将使用该证书签名，避免每次编译更新都需要重新授予“屏幕录制”权限。

---

## 官网展示页

宣传网站代码位于 `website/` 目录（基于 Vite + React 开发）：

```bash
cd website && npm install && npm run dev
```

---

## 开发计划 (Roadmap)

- [ ] 录屏时可视化按键按压显示
- [ ] 长截图（滚动长图拼接）
- [ ] Apple Developer ID 签名与公证分发

---

## 原项目致谢

ShotX 原版由 [@aimen08](https://github.com/aimen08) 开发（原项目地址：[aimen08/shotx](https://github.com/aimen08/shotx)）。本项目为其简体中文汉化及优化版本。

---

<div align="center">
<sub>基于 Swift、AppKit 与 SwiftUI 构建。</sub>
</div>
