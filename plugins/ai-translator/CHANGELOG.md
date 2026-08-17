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

# v1.1.0 Release Notes (2026-08-08)

## New Features
- **Popup Mode Support**: Added popup window mode support triggered from QuickAction panel, rendering a simplified translation interface optimized for small popup windows
- **Stop-on-Close**: Added `stopOnClose: true` configuration to automatically stop the sidecar process when the popup window is closed, freeing system resources

<details>
<summary>中文说明</summary>

# v1.1.0 更新说明 (2026-08-08)

## 新增功能
- **Popup 模式支持**：新增从快捷操作面板触发的 popup 窗口模式，渲染精简翻译界面，针对小窗口优化
- **关闭即停止**：新增 `stopOnClose: true` 配置，关闭 popup 窗口时自动停止 sidecar 进程，释放系统资源

</details>

---

# v1.0.2 Release Notes (2026-08-08)

## Bug Fixes
- **Popup Mode Detection**: Fixed an issue where the plugin rendered the full InApp layout instead of the simplified Popup UI when triggered from the QuickAction panel on some systems. Mode detection now primarily relies on the iframe window name (set by core v0.36.2+), which is immune to WebView runtime differences in blob URL hash handling; the previous hash-based detection is retained as a fallback
- **Diagnostics**: The plugin now reports its detected runtime mode to the core frontend log, making future popup/inapp identification issues easier to diagnose

<details>
<summary>中文说明</summary>

# v1.0.2 更新说明 (2026-08-08)

## 修复
- **Popup 模式检测**：修复部分系统中从快捷操作面板触发时渲染完整 InApp 界面而非精简 Popup 界面的问题。模式检测现主要依赖 iframe 窗口名（由核心 v0.36.2+ 设置），不受 WebView 运行时对 blob URL hash 处理差异的影响；原 hash 检测保留作为兼容通道
- **诊断能力**：插件现在会向核心前端日志上报实际识别到的运行模式，便于后续定位 popup/inapp 识别问题

</details>

---

# v1.0.1 Release Notes (2026-08-08)

## Improvements
- **Public Release**: Changed from private to public plugin, now visible and installable from the marketplace

<details>
<summary>中文说明</summary>

# v1.0.1 更新说明 (2026-08-08)

## 改进
- **公开发布**：从私有插件改为公共插件，现可在商城中查看和安装

</details>

---

# v1.0.0 Release Notes (2026-08-08)

## New Features
- **AI-Powered Translation**: One-click translation of selected text using AI services (DeepSeek, OpenAI, Claude, Ollama) configured in the core application
- **Multi-Target Language**: Support for Chinese, English, Japanese, Korean, and more target language switching
- **Context Action Integration**: Automatically appears in the Quick Action panel when text is selected, triggered via middle-click or custom hotkey
- **Standalone Popup Mode**: Translation results displayed in an independent popup window (400×480) with one-click copy
- **Automatic Source Language Detection**: AI automatically identifies the source language without manual selection

<details>
<summary>中文说明</summary>

# v1.0.0 更新说明 (2026-08-08)

## 新增功能
- **AI 驱动翻译**：选中文字后一键翻译，支持核心程序配置的 AI 服务（DeepSeek、OpenAI、Claude、Ollama 等）
- **多目标语言**：支持中文、英文、日语、韩语等目标语言切换
- **快捷操作集成**：选中文本后自动出现在快捷操作面板中，通过鼠标中键或自定义快捷键触发
- **独立弹窗模式**：翻译结果在独立弹窗中展示（400×480），支持一键复制
- **自动源语言识别**：AI 自动识别源语言，无需手动选择

</details>
