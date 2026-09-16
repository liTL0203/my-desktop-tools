# v1.3.1 更新说明 (2026-09-16)

## 新增
- JSON 折叠标记支持 VSCode 式点击展开/收起

## 优化
- 小窗口布局优化，长行滚动更顺滑
- 快速打开与粘贴响应更快
- 代码质量加固

---

# v1.3.0 Release Notes (2026-09-12, 未发布增补 2026-09-15)

## Performance
- **Instant Format on Paste / QA Direct-Open**: pasting content or opening via QuickAction no longer sits through the 400ms typing-debounce before auto-formatting — results render immediately (debounce now applies to manual typing only)
- **Window Reuse for Faster QA Round-Trips**: `allowMultiple` is now `false` — re-triggering from QuickAction (or Quick Launcher) focuses the existing window and streams the new content into it, instead of paying the full cold window+page load every time

## Features
- **Responsive Layout for Small Windows**: Toolbar redesigned with a 3-zone structure (brand / high-frequency actions / overflow menu). High-frequency actions (Validate / Format / Minify / Paste / Copy) are always one click away; low-frequency actions are grouped into a single "More" menu (Data / Editor / Panels)
- **Adaptive Breakpoints**: ≥1140px full labels; 840–1139px icon-only buttons with tooltips; <840px dual-pane tab mode (Editor / Result) with slimmed status bar
- **Smaller Minimum Window**: standalone minWidth 900 → 720, enabling a true compact popup form
- **Snippet Drawer Adaptivity**: drawer now uses `min(560px, 100%)` — full-width on small windows instead of squeezing both columns

## Fixes
- **Horizontal Scrollbar in Editor**: Long JSON lines no longer bleed under the right panel — the editor width is now properly constrained (`min-width: 0` on the flex chain), so the horizontal scrollbar appears and works; scrollbar thumb is guaranteed visible via standard `scrollbar-color` (with `::-webkit-scrollbar` fallback for older engines) and higher thumb contrast

<details>
<summary>中文说明</summary>

# v1.3.0 更新说明 (2026-09-12，未发布增补 2026-09-15)

## 性能
- **粘贴/QA 直达即时格式化**：粘贴内容或从快捷操作直达打开时不再白等 400ms 键入防抖，格式化结果立即呈现（防抖仅对手动键入生效）
- **窗口复用加速 QA 往返**：`allowMultiple` 改为 `false`——再次从快捷操作（或快捷启动）触发时聚焦已有窗口并把新内容送入，不再每次支付全新窗口+页面冷加载

## 功能
- **小窗口响应式布局**：工具栏重构为三段结构（品牌区 / 高频操作 / 收纳菜单）。高频操作（校验/格式化/压缩/粘贴/复制）任意宽度一键直达；低频功能统一收进「⋯ 更多」菜单（数据/编辑器/面板分组）
- **自适应断点**：≥1140px 完整文字按钮；840–1139px 图标化（悬停显示全名）；<840px 双面板 tab 化（编辑/结果）+ 状态栏次要信息隐藏
- **更小的最小窗口**：独立窗口 minWidth 900 → 720，支持真正的小弹窗形态
- **片段抽屉自适应**：抽屉宽度改为 min(560px, 100%)，小窗口下全屏展示不再双列互挤

## 修复
- **编辑器横向滚动条**：超长 JSON 行不再延伸到右侧面板底下被盖住——修复 flex 链缺失 `min-width: 0` 导致编辑器被内容撑宽、横向滚动条永不出现的问题；滑块通过标准 `scrollbar-color`（旧内核回退 `::-webkit-scrollbar`）保证可见，并提高对比度

</details>

---

# v1.2.1 Release Notes (2026-08-18)

## Bug Fixes
- **Cascading Dialog Close**: Fixed multi-dialog cascading close issue when closing from a table view context
- **Table View Enhancements**: Improved table view functionality and interaction

<details>
<summary>中文说明</summary>

# v1.2.1 更新说明 (2026-08-18)

## 修复
- **多弹窗连锁关闭**：修复从表格视图上下文关闭时多弹窗连锁关闭问题
- **表格视图增强**：改进表格视图功能与交互

</details>

---

# v1.2.0 Release Notes (2026-08-17)

## Maintenance
- Version sync release: no functional changes; aligned metadata versioning with the latest release pipeline

<details>
<summary>中文说明</summary>

# v1.2.0 更新说明 (2026-08-17)

## 维护
- 版本同步发布：无功能性变更，与最新发版流程的元数据版本对齐

</details>

---

# v1.1.3 Release Notes (2026-08-13)

## Bug Fixes
- **CodeMirror Content Bleed-through**: Fixed a visual issue where editor content from the input panel would bleed through and appear on top of other panels (FilterSlotsPanel, ResultPanel) in certain layout configurations

<details>
<summary>中文说明</summary>

# v1.1.3 更新说明 (2026-08-13)

## 修复
- **CodeMirror 内容穿透**：修复特定布局配置下输入面板的编辑器内容穿透显示到其他面板（FilterSlotsPanel、ResultPanel）上方的视觉问题

</details>

---

# v1.1.1 Release Notes (2026-08-12)

## Improvements
- **CodeMirror Editor**: Enhanced editor update handling with better state synchronization and cursor position management for large JSON documents

<details>
<summary>中文说明</summary>

# v1.1.1 更新说明 (2026-08-12)

## 改进
- **CodeMirror 编辑器**：增强编辑器更新处理，优化大 JSON 文档的状态同步和光标位置管理

</details>

---

# v1.1.0 Release Notes (2026-08-10)

## New Features
- **Table View Enhancements**: Improved table view with better column alignment, hover details, and double-click cell copy functionality for large datasets
- **Editor Improvements**: Enhanced CodeMirror editor integration with better update handling and layout state management
- **Toolbar Refinement**: Updated toolbar component with cleaner action grouping and improved i18n support
- **Type System Updates**: Synchronized TypeScript and Rust type definitions for better frontend-sidecar communication

<details>
<summary>中文说明</summary>

# v1.1.0 更新说明 (2026-08-10)

## 新增功能
- **表格视图增强**：改进表格视图，优化列对齐、悬停详情、双击单元格复制功能，适配大数据集
- **编辑器改进**：增强 CodeMirror 编辑器集成，优化更新处理与布局状态管理
- **工具栏优化**：更新工具栏组件，操作按钮分组更清晰，改进国际化支持
- **类型系统更新**：同步 TypeScript 和 Rust 类型定义，改善前端与 Sidecar 通信

</details>

---

# v1.0.2 Release Notes (2026-08-10)

## Bug Fixes
- **Worker Cross-Origin Fix**: Fixed `Failed to construct 'Worker'` error in standalone/desktop window mode by switching from URL-based Worker construction to Vite's `?worker&inline` import, which inlines the Worker script as a base64 data URL and completely bypasses the Tauri v2 same-origin policy restriction (`asset.localhost` vs `tauri.localhost`)

<details>
<summary>中文说明</summary>

# v1.0.2 更新说明 (2026-08-10)

## 修复
- **Worker 跨域修复**：修复独立窗口（desktop）模式下 `Failed to construct 'Worker'` 错误。将 Worker 构造方式从 URL 模式改为 Vite 的 `?worker&inline` 导入，将 Worker 脚本内联为 base64 data URL，完全绕过 Tauri v2 同源策略限制（`asset.localhost` vs `tauri.localhost`）

</details>

---

# v1.0.1 Release Notes (2026-08-10)

## Improvements
- **Pipeline Error Logging**: Added frontend diagnostic logging to all JSON pipeline catch blocks (parse, format, minify, auto-format), writing structured error details to `frontend.log` for remote troubleshooting without blocking the UI

<details>
<summary>中文说明</summary>

# v1.0.1 更新说明 (2026-08-10)

## 改进
- **流水线错误日志**：为 JSON 流水线的所有 catch 块（解析、格式化、压缩、自动格式化）添加前端诊断日志，将结构化错误详情写入 `frontend.log`，便于远程排查且不阻塞 UI

</details>

---

# v1.0.0 Release Notes (2026-08-10)

## New Features
- **Format & Minify**: JSON beautify (2/4 space indent) and single-line minify with auto-parse on input
- **JS Processing Engine**: Custom JS function body to process JSON data, structured syntax/runtime error feedback, infinite loop timeout auto-termination
- **Multi-dimensional Visualization**: Auto-intelligent view selection (image > table > tree > text)
  - Table view: virtual scrolling (100k rows smooth), column sorting, hover details, double-click copy
  - Image view: base64 / URL image grid, click to enlarge
  - Tree view: lazy expansion + render limit protection
  - Text view: JSON syntax highlighting, line numbers, paginated loading
- **JS Snippet Library**: Grouped management, sorting, one-click insert, quick run, persisted to plugin data directory
- **Local Files**: Native dialog open/save JSON files (50MB limit protection)
- **Layout**: Drag-resizable input panel (20%~60%), double-click collapse, fullscreen preview, preference persistence
- **Status Bar**: Node count, data size, parse/process time, current view real-time display

## Stability
- All heavy computation (parse/format/JS execution/analysis) runs in Web Worker, zero UI blocking
- Worker exception/timeout auto-rebuild, top-level error panel fallback, no white screen
- Config and snippet atomic writes (.tmp + rename), auto-fallback with .bak on corruption

<details>
<summary>中文说明</summary>

# v1.0.0 更新说明 (2026-08-10)

## 新增功能
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

## 稳定性
- 全部重计算（解析/格式化/JS 执行/分析）在 Web Worker 中运行，UI 零阻塞
- Worker 异常/超时自动重建，顶层错误面板兜底，杜绝白屏
- 配置与片段原子写入（.tmp + rename），损坏自动回退并保留 .bak

</details>

---

# v0.1.0 (2026-08-09)

Initial development version. Feature set identical to v1.0.0.

<details>
<summary>中文说明</summary>

# v0.1.0 更新说明 (2026-08-09)

初始开发版本，功能与 v1.0.0 相同。

</details>
