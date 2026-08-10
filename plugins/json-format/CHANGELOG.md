# v1.1.0 Release Notes (2026-08-10)

## New Features
- **Table View Enhancements**: Improved table view with better column alignment, hover details, and double-click cell copy functionality for large datasets
- **Editor Improvements**: Enhanced CodeMirror editor integration with better update handling and layout state management
- **Toolbar Refinement**: Updated toolbar component with cleaner action grouping and improved i18n support
- **Type System Updates**: Synchronized TypeScript and Rust type definitions for better frontend-sidecar communication

---

# v1.0.2 Release Notes (2026-08-10)

## Bug Fixes
- **Worker Cross-Origin Fix**: Fixed `Failed to construct 'Worker'` error in standalone/desktop window mode by switching from URL-based Worker construction to Vite's `?worker&inline` import, which inlines the Worker script as a base64 data URL and completely bypasses the Tauri v2 same-origin policy restriction (`asset.localhost` vs `tauri.localhost`)

---

# v1.0.1 Release Notes (2026-08-10)

## Improvements
- **Pipeline Error Logging**: Added frontend diagnostic logging to all JSON pipeline catch blocks (parse, format, minify, auto-format), writing structured error details to `frontend.log` for remote troubleshooting without blocking the UI

---

# v1.0.0 Release Notes (2026-08-10)

---

## 更新日志

### v1.0.0 (2026-08-10)

### ✨ 新功能

- **格式化与压缩**：JSON 美化（2/4 空格缩进）与单行压缩，输入即自动解析
- **JS 处理引擎**：自定义 JS 函数体处理 JSON 数据，语法/运行时错误结构化反馈，死循环超时自动终止
- **多维可视化**：自动智能判断视图（图片 > 表格 > 树形 > 文本）
  - 表格视图：虚拟滚动（10 万行流畅）、列排序、悬停详情、双击复制
  - 图片视图：base64 / URL 图片网格、点击放大预览
  - 树形视图：惰性展开 + 渲染上限保护
  - 文本视图：JSON 语法高亮、行号、分页加载
- **JS 片段库**：分组管理、排序、一键插入、快捷运行，持久化到插件数据目录
- **本地文件**：原生对话框打开/保存 JSON 文件（50MB 上限保护）
- **布局优化**：输入面板可拖拽宽度（20%~60%）、双击折叠、全屏预览、偏好持久化
- **状态栏**：节点数、数据大小、解析/处理耗时、当前视图实时显示

### 🛡️ 稳定性

- 全部重计算（解析/格式化/JS 执行/分析）在 Web Worker 中运行，UI 零阻塞
- Worker 异常/超时自动重建，顶层错误面板兜底，杜绝白屏
- 配置与片段原子写入（.tmp + rename），损坏自动回退并保留 .bak

---

## v0.1.0 (2026-08-09)

### ✨ 新功能

- **格式化与压缩**：JSON 美化（2/4 空格缩进）与单行压缩，输入即自动解析
- **JS 处理引擎**：自定义 JS 函数体处理 JSON 数据，语法/运行时错误结构化反馈，死循环超时自动终止
- **多维可视化**：自动智能判断视图（图片 > 表格 > 树形 > 文本）
  - 表格视图：虚拟滚动（10 万行流畅）、列排序、悬停详情、双击复制
  - 图片视图：base64 / URL 图片网格、点击放大预览
  - 树形视图：惰性展开 + 渲染上限保护
  - 文本视图：JSON 语法高亮、行号、分页加载
- **JS 片段库**：分组管理、排序、一键插入、快捷运行，持久化到插件数据目录
- **本地文件**：原生对话框打开/保存 JSON 文件（50MB 上限保护）
- **布局优化**：输入面板可拖拽宽度（20%~60%）、双击折叠、全屏预览、偏好持久化
- **状态栏**：节点数、数据大小、解析/处理耗时、当前视图实时显示

### 🛡️ 稳定性

- 全部重计算（解析/格式化/JS 执行/分析）在 Web Worker 中运行，UI 零阻塞
- Worker 异常/超时自动重建，顶层错误面板兜底，杜绝白屏
- 配置与片段原子写入（.tmp + rename），损坏自动回退并保留 .bak
