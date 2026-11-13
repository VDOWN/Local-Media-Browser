# Local Media Browser · 本地媒体浏览器

A single-file, serverless local media browser powered by the File System Access API.
Browse images, videos and audio in a local folder — no upload, no backend, no third-party services.

一个基于浏览器 File System Access API 的**HTML**代码方式的本地媒体浏览器。
无需后端、无需上传，直接在浏览器中浏览本地文件夹里的图片、视频和音频。
已实现简单且快速浏览、放大、缩小，播放音视频文件，或直接删除媒体（包括图片、音频、视频类型）文件等功能。

可直接访问：  https://vdown.cn/lmb 即可体验。

---

## 💡 Motivation · 项目初衷

最初的需求其实非常简单：**只是为了做一个纯粹的本地相册，方便浏览硬盘里用手机拍摄的照片。** 

几年前，我曾尝试寻找过各种开源的相册源码，但始终未能找到完全契合自己心意的方案，总有些功能和交互不够顺手。

不得不感叹如今 AI 的强大。仅仅用了一个晚上的时间，在不断提出需求、打磨细节、修复 Bug 的过程中，AI 帮助我将最初的一个单文件 HTML 脚本，逐渐重构、演变成了如今这个结构清晰、功能完善的多文件项目，完美实现了所有我想要的特性。

> The initial motivation was quite simple: **I just wanted a pure local photo album to easily browse photos taken with my phone on my hard drive.** 
> 
> Years ago, I tried searching for various open-source photo album source codes, but none of them perfectly met my requirements. 
> 
> I have to marvel at how powerful today's AI has become. In just one night, through continuous requirement iterations and fine-tuning of details, the AI helped me transform an initial single-file HTML script into a well-structured, feature-complete multi-file project, perfectly implementing all the features I desired.

---

## ✨ Features · 功能特性

### Browse & Display · 浏览与展示
- 📁 **Directory tree** — recursively scan a folder and all subfolders, browse like a file explorer. (递归扫描，像资源管理器一样浏览)
- 🖼️ **Smart thumbnails** — Canvas-generated image thumbs, first-frame video covers, and audio placeholders. (智能缩略图，视频抽帧，音频占位)
- 🔍 **Hover zoom** — magnify image thumbnails on hover with adjustable zoom factor. (悬停放大图片预览)
- 📐 **Resizable sidebar** — drag the divider to resize (180–640px). (可拖动调整侧边栏宽度)

### Lightbox & Playback · 灯箱与播放
- 🖼️ **Image view** — scroll to zoom, drag to pan, double-click to reset. (图片滚轮缩放、拖拽)
- 🎬 **Native media** — play video and audio with native browser controls. (原生音视频播放器)
- ‹ › **Nav arrows** — click the on-screen arrows to switch items. (屏幕左右点击箭头切换)
- ⌨️ **Keyboard shortcuts** — `← →` switch, `Space/Enter` play-pause/next, `Delete` remove, `Esc` close.

### Management & Info · 管理与信息
- ✅ **Batch selection** — select multiple items to delete in bulk. (批量勾选与操作)
- ♻️ **Trash & Restore** — move to `.gallery-trash` and restore to original paths. (移入回收站并保留原目录结构，支持恢复)
- 📷 **EXIF Data** — display camera parameters (Make, Model, Aperture, ISO, etc.) for JPEGs. (读取并展示 JPEG 照片的 EXIF 信息)
- 📄 **File Info Fallback** — show date, size, and format when EXIF is absent. (无 EXIF 时显示文件日期、大小和格式)

### Playback & Theme · 播放与主题
- 🔁 **Slideshow** — auto-advance items with a customizable interval. Auto-plays media when entering lightbox. (幻灯片自动轮播，音视频自动播放)
- 🎨 **Themes** — Dark, Light, Blue. (深灰、灰白、浅蓝三种主题)
- 🌐 **Bilingual** — Chinese / English UI with **auto-detect system language**. (中英双语，自动检测系统语言)

![Lightbox](screenshots/lightbox.png)

---

## 🚀 Quick Start · 快速开始

### Option 1: Direct Open · 直接打开
Download the repository and open `index.html` in **Chrome** or **Edge** (86+).
> ⚠️ Opening via `file://` may block `showDirectoryPicker`. Use a local server if it fails.

### Option 2: Local Server · 本地服务器
```bash
python -m http.server 8000
