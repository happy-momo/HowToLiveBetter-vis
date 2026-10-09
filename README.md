<div align="center">

<img src="https://raw.githubusercontent.com/eternity4719/HowToLiveBetter/main/og.png" alt="高性价比人生指南" width="720">

# 高性价比人生指南 · 书页版

https://happy-momo.github.io/HowToLiveBetter-vis/

**HowToLiveBetter · Book-Viewer Edition**

一本竖立、从顶边往下掀的相册式网页书，用真实的 3D 翻页效果阅读《高性价比人生指南》全部 670 条内容。

A vertical top-flip web book that lets you read all 670 entries of *HowToLiveBetter* with realistic 3D page-turning.

</div>

---

## 简介 / About

这是[《高性价比人生指南》](https://github.com/eternity4719/HowToLiveBetter)的一个衍生阅读界面：把正文做成一本像挂在墙上的翻页簿，从顶边掀开下一页，带纸张质感、卷曲高光、桌面阴影。目录、书签、阅读进度都收在左侧面板里，随时呼出。

This is an alternative reader for [*HowToLiveBetter*](https://github.com/eternity4719/HowToLiveBetter): the full text is presented as a wall-style flip book that turns from the top edge, with paper texture, curl highlights, and desk-shadow depth. A side panel holds the table of contents, bookmarks, and reading progress — open it any time.

正文版权归原作者所有，按 [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) 发布。本仓库的代码按 MIT 许可。

The original content is released under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/), © the original author. The code in this repository is MIT-licensed.

## 功能 / Features

| 中文 | English |
| --- | --- |
| 顶边下掀的 3D 翻页效果 | Top-edge 3D page-turning animation |
| 670 条建议自动分页，条目不跨页 | 670 entries auto-paginated, no entry split across pages |
| 桌面 / 手机同等适配（竖屏单栏） | Equally polished on desktop and mobile (single-column portrait) |
| 三 tab 面板：目录、书签、进度 | 3-tab panel: Table of Contents, Bookmarks, Progress |
| 目录实时高亮正在读的那一节和那一条 | TOC highlights the section & entry you're on in real time |
| 书签本地保存，可导出/导入 JSON 备份 | Bookmarks in localStorage, exportable / importable as JSON |
| URL 带阅读位置，分享链接可复原 | URL carries reading position — share a link to resume |
| `prefers-reduced-motion` 自动降级为淡入淡出 | Auto-degrades to fade transition under `prefers-reduced-motion` |

## 操作 / Controls

| 操作 | Action |
| --- | --- |
| ↓ / → / PageDown / 上滑（触屏） | 翻下一页 / Next page |
| ↑ / ← / PageUp / 下滑（触屏） | 翻回上一页 / Previous page |
| 左侧 ☰ 按钮 | 打开面板 / Open panel |
| `#entry-节号-条号` | 直接定位到某条 / Deep-link to an entry |

## 部署 / Deployment

纯静态页面，不需要后端。任何静态托管都能跑。

It's a pure static site — no backend needed. Works on any static host.

### GitHub Pages

把本仓库推到 GitHub，在仓库设置里开 Pages（Settings → Pages → Source: Deploy from a branch → `main` → `/ (root)`），即可访问：

Push this repo to GitHub and enable Pages (Settings → Pages → Source: Deploy from a branch → `main` → `/ (root)`). The site is then available at:

```
https://<your-username>.github.io/HowToLiveBetter-vis/
```

### 本地预览 / Local preview

```bash
python3 -m http.server 8000
# 然后打开 http://localhost:8000
# then open http://localhost:8000
```

> ⚠️ 不能直接双击 `index.html` 打开——浏览器禁止网页用 `file://` 读本地 JSON 文件。必须走 HTTP 服务。
>
> ⚠️ Do NOT double-click `index.html` — browsers block `fetch()` of local files under `file://`. Always serve over HTTP.

## 文件结构 / Structure

```
index.html        # 页面外壳
app.js            # 主逻辑：加载、测量、分页、翻页、书签、面板
style.css         # 纸感 / 透视 / 3D 翻页 / 面板 / 响应式
paginate.mjs      # 纯函数自动分页（与原仓库 tools/book-viewer 共用）
corpus.json       # 正文数据（由原仓库生成器产出，670 条 / 34 节 / 9 篇长文）
```

## 来源 / Source

- 原项目 / Original: [github.com/eternity4719/HowToLiveBetter](https://github.com/eternity4719/HowToLiveBetter)
- 数据生成器 / Data generator: `tools/book-viewer/build.mjs`（在原仓库中 / in the source repo）
- 官方在线检索版 / Official search UI: [eternity4719.github.io/HowToLiveBetter/](https://eternity4719.github.io/HowToLiveBetter/)

本仓库的正文与元数据 (`corpus.json`) 从原仓库同步，可能落后于最新版本。以原仓库中文原文为准。

The content and metadata (`corpus.json`) in this repo are synced from the source project and may lag behind the latest version. The Chinese original at the source repository is authoritative.

## 许可 / License

- 正文 / Content: [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/)，请注明出处「高性价比人生指南」并附上原仓库链接。
- 代码 / Code: MIT
