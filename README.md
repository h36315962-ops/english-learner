# 英语学习伴侣 · YouTube English Learner

纯网页版英语学习工具：粘贴 YouTube 链接看视频，导入字幕文件后逐句中英对照，长按/选中陌生单词即可查词并收藏进单词本。

无需安装、无需服务器，手机/电脑浏览器直接打开即可使用。

## 使用方法

1. **粘贴 YouTube 视频链接**，点「加载视频」开始播放（手机可全屏）。
2. **获取字幕**（纯网页版受浏览器安全限制，无法自动抓取字幕）：
   - 电脑安装 [yt-dlp](https://github.com/yt-dlp/yt-dlp) 后运行：
     ```
     yt-dlp --write-auto-sub --sub-lang en --skip-download -o "%(id)s" 视频链接
     ```
   - 或使用在线字幕站（如 downsub、notta 等）下载 .srt 文件。
3. 点「**导入字幕**」上传 .srt/.vtt/.txt，页面自动逐句翻译为中文，并随播放进度同步高亮。
4. **长按（手机）/ 拖动选中（电脑）**字幕里的单词即可查词，点「加入单词本」收藏。
5. 单词本支持搜索、删除、导出（TXT/CSV/JSON）；换设备时可导出 JSON 再「导入」合并。

## 功能特性

- 左侧/上方：YouTube 视频播放器，桌面端支持拖动分隔条调整布局
- 字幕面板：中英逐句对照、播放进度同步高亮、点句跳转、循环当前句
- 查词：Datamuse 英文释义 + Google 翻译中文释义（纯浏览器直连）
- 单词本：本地存储（localStorage）、导出/导入同步
- 完全免费、无广告、数据仅保存在你的浏览器

## 部署

本仓库即 GitHub Pages 站点（根目录 `index.html`）。访问地址由仓库 Settings → Pages 提供。

## 技术说明

- 播放器：YouTube IFrame API
- 翻译：Google 翻译网页接口（`translate.googleapis.com`）+ MyMemory 兜底
- 查词：Datamuse API + Google 翻译
- 字幕解析：支持 SRT / VTT / 纯文本时间轴（`mm:ss 文本`）
