# v2.5.0 更新说明 (2026-09-25)

## 新增
- ESC 键行为修复——菜单/弹层关闭不再误触页面退出

---

# v2.4.2 更新说明 (2026-09-23)

## 优化
- 维护性同步：随核心 1.2.14 发布周期对齐（构建与工程配置），无功能变化

---

# v2.4.1 更新说明 (2026-09-16)

## 修复
- 修复市场安装的插件在侧边栏/气泡显示占位图标的问题——ZIP 现已包含插件图标文件
- 构建配置适配 pnpm v12（工程内部，不影响使用）

---

# v2.4.0 更新说明 (2026-09-16)

## 新增
- 词典增强翻译：命中词典时展示结构化富内容——词语/句子/段落三种形态，含语言与模式徽章、一键复制与重译
- 词典增强开关：可在插件设置中自主控制启用与否

## 优化
- 上下文触发规则更精准

---

# v2.4.0 更新说明 (2026-09-16)

## 新增
- 词典增强翻译：命中词典时展示结构化富内容——词语/句子/段落三种形态，含语言与模式徽章、一键复制与重译
- 词典增强开关：可在插件设置中自主控制启用与否

## 优化
- 上下文触发规则更精准

---

# v2.3.0 更新说明 (2026-09-16)

## 优化
- 启动性能三期优化——从快捷启动 / 快捷操作打开更快
- 快捷操作内容识别精度同步适配

---

# v2.2.0 更新说明 (2026-09-16)

## 新增
- 全新 v2 翻译工作台：双栏布局，翻译流程更清晰
- 翻译模型可选：对接核心模型字典，按任务选择合适的模型

## 优化
- 代码质量与稳定性加固

---

# v2.1.0 Release Notes (2026-09-14)

## New Features
- **Translation Model Selection (Model Dictionary)**: Pick a translation model from the system-wide model dictionary (AI Service → Models); translation requests now carry the selected model via the gateway's per-session model channel
- **Follow-Default Mode**: By default the plugin follows your system default model — switching it in the dictionary applies to the next translation immediately, no plugin restart needed
- **Migration Notice**: AI models are now managed centrally; providers and API keys live in AI Service → Models

## Notes
- The model picker reads the core model dictionary; on older cores without dictionary read access the picker degrades to "follow default" with a hint (translation keeps working)
- Models are filtered to translation-capable entries (chat purpose, text type) and shown as "Provider · Model"

<details>
<summary>中文说明</summary>

# v2.1.0 更新说明 (2026-09-14)

## 新增功能
- **翻译模型选择（模型字典）**：可从系统模型字典（AI 服务 → 模型）中选择翻译模型，翻译请求经网关会话级模型通道携带所选模型
- **跟随默认模式**：默认跟随系统默认模型——在字典中切换默认模型后下一次翻译立即生效，无需重启插件
- **迁移提示**：AI 模型已升级为系统统一管理，提供方与密钥在「AI 服务 → 模型」中维护

## 说明
- 模型选择器读取核心模型字典；旧版核心无字典读取权限时自动降级为"跟随默认"并提示（翻译功能不受影响）
- 模型列表按翻译能力过滤（chat 用途 + 文本类型），以"提供方 · 模型名"展示

</details>

---



# v2.0.0 Release Notes (2026-09-08)

## New Features
- **Multi-Target Translation**: Popup now supports selecting up to 4 target languages at once — each gets its own result card with independent copy and retry (R2-B layout)
- **Expanded Language System**: Built-in library of 12 languages with a configurable quick-language pool; auto-detected source language badge
- **Redesigned InApp Layout**: Cleaner vertical workflow (Plan B) — slim header with live version badge, input card with char/word count and swap button, result card with copy/copy-both
- **History Upgrade**: Searchable history with favorites pinning, per-entry delete, clear confirmation, and configurable capacity (20/50/100/200)
- **Custom Prompt Template**: Define your own translation prompt with the {lang} placeholder, on top of 3 presets
- **Popup Manual Input**: Empty popup now doubles as a manual translation input
- **Auto-translate Toggle**: Optionally require a manual click before consuming AI requests

## Bug Fixes
- **Duplicate Translation on Refocus**: Pending context is now consumed on read — refocusing the popup no longer re-translates the same text and no longer resets your language choice
- **Default Language Ignored**: Quick Action no longer overrides your configured default target language (legacy v1 configs migrate automatically)
- **Version Badge Sync**: The InApp version badge now reads the sidecar version dynamically instead of showing a stale hardcoded value
- **History ID Collision**: Same-second translations no longer produce duplicate list keys
- **Removed Dead Model Selector**: The model dropdown never took effect since the AI gateway took over model routing; it is now gone

<details>
<summary>中文说明</summary>

# v2.0.0 更新说明 (2026-09-08)

## 新增功能
- **多目标翻译**：Popup 支持同时选择最多 4 门目标语言，每门语言一张结果卡，独立复制与重译（R2-B 布局）
- **语言系统扩展**：内置 12 种语言库，快捷语言池可自定义；源语言自动识别徽标
- **InApp 界面重排**：纵向流式布局（方案 B）——瘦头部动态版本徽标、输入卡带字数统计与互换按钮、结果卡支持复制译文/复制双语
- **历史升级**：搜索、收藏置顶、单条删除、清空二次确认、容量可调（20/50/100/200）
- **自定义 Prompt 模板**：在 3 个预设之外用 {lang} 占位符编写自己的翻译模板
- **Popup 手动输入**：空弹窗可直接输入文本翻译
- **自动翻译开关**：可关闭选中即译，手动确认后再消耗 AI 请求

## 修复
- **重聚焦重复翻译**：暂存上下文改为读取即消费，弹窗重新聚焦不再重复翻译同一段文字、不再重置语言选择
- **默认语言被忽略**：快捷操作不再用硬编码"中文"覆盖你配置的默认目标语言（v1 旧配置自动迁移）
- **版本徽标同步**：InApp 版本徽标改为动态读取 sidecar 版本，不再显示过期的硬编码值
- **历史 ID 冲突**：同一秒内的多次翻译不再产生重复列表 key
- **移除失效模型选择器**：AI 网关接管模型路由后该下拉框从未生效，现已移除

</details>

---



# v1.2.1 Release Notes (2026-08-18)

## Improvements
- **Marketplace Icon Loading**: Optimized plugin market icon loading mechanism with unified sponsorship terminology

<details>
<summary>中文说明</summary>

# v1.2.1 更新说明 (2026-08-18)

## 改进
- **商城图标加载**：优化商城插件图标加载机制，统一付费相关术语为赞助

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
