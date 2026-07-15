# Changelog

> All version release notes. Latest version first.

---

# v0.23.0 (2026-07-15)

## Bug 修复
- **更新安装修复**: 修复更新安装过程中的文件锁定问题，提升自动更新成功率

## 新增功能
- **双语更新说明**: 更新通知弹窗支持中英文双语显示，国际化体验进一步提升

## 优化改进
- **文档体系**: 完善版本历史文档结构，新增快速开始和 API 参考文档

---

# v0.22.0 Release Notes (2026-07-15)

## New Features
- **Markdown Rendering Support**: Release notes in update notification popups now support Markdown format parsing, with a new universal Markdown parsing utility module for improved formatting and readability

<details>
<summary>中文说明</summary>

# v0.22.0 更新说明 (2026-07-15)

## 新增功能
- **Markdown 渲染支持**: 更新通知弹窗中的版本说明支持 Markdown 格式解析，新增通用 Markdown 解析工具模块，提升更新信息的排版和可读性

</details>

---

# v0.21.0 Release Notes (2026-07-14)

## New Features
- **Internationalization (i18n)**: Integrated vue-i18n for full-stack internationalization architecture, supporting Chinese/English language switching across settings page, statistics panel, plugin names, and other core UI
- **Plugin Name Localization**: Plugin display names now automatically switch based on system language, improving the multilingual user experience

## Improvements
- **Plugin Settings Architecture**: Extracted plugin settings update logic into standalone functions, reducing coupling and improving maintainability
- **Documentation Cleanup**: Removed outdated quick-start guide and API reference docs to reduce maintenance burden

<details>
<summary>中文说明</summary>

# v0.21.0 更新说明 (2026-07-14)

## 新增功能
- **国际化（i18n）支持**: 集成 vue-i18n，实现全栈国际化架构，支持中英文切换，覆盖设置页、统计面板、插件名称等核心界面
- **插件名称国际化**: 插件显示名称支持根据系统语言自动切换，提升多语言用户体验

## 优化改进
- **插件设置架构**: 提取插件设置更新逻辑为独立函数，降低耦合度，提升代码可维护性
- **文档精简**: 移除过时的快速开始指南和 API 参考文档，减少维护负担

</details>
# v0.21.0 更新说明 (2026-07-14)

## 新增功能
- **国际化（i18n）支持**: 集成 vue-i18n，实现全栈国际化架构，支持中英文切换，覆盖设置页、统计面板、插件名称等核心界面
- **插件名称国际化**: 插件显示名称支持根据系统语言自动切换，提升多语言用户体验

## 优化改进
- **插件设置架构**: 提取插件设置更新逻辑为独立函数，降低耦合度，提升代码可维护性
- **文档精简**: 移除过时的快速开始指南和 API 参考文档，减少维护负担

---

# v0.20.0 Release Notes (2026-07-14)

## New Features
- **Brand New App Icon**: Adopted Apple HIG design style, combining "paw print + toolbox" concept with Apple system blue (#007aff / #0a84ff) gradient and frosted glass texture. Fully replaced the old icon to enhance brand recognition and visual refinement

<details>
<summary>中文说明</summary>

# v0.20.0 更新说明 (2026-07-14)

## 新增功能
- **全新应用图标**: 采用 Apple HIG 设计风格，融合「爪印 + 工具箱」概念，Apple 系统蓝（#007aff / #0a84ff）渐变配色搭配毛玻璃质感，全面替换旧版图标，提升品牌识别度与视觉精致感

</details>

---

# v0.19.0 Release Notes (2026-07-14)

## New Features
- **Custom Title Bar**: Implemented a custom window title bar to replace the native Windows window decoration, providing a more refined cross-platform consistent experience
- **Update Detection Source Tracking**: Added update detection source options to distinguish between manual checks and automatic detections, enabling precise tracking of update trigger paths

## Improvements
- **Documentation Cleanup**: Removed outdated quick-start guide and API reference docs to reduce maintenance burden

<details>
<summary>中文说明</summary>

# v0.19.0 更新说明 (2026-07-14)

## 新增功能
- **自定义标题栏**: 实现自定义窗口标题栏，替换原生 Windows 窗口装饰，提供更精致的全平台一致体验
- **更新检测来源标记**: 新增更新检测来源选项，区分手动检查与自动检测，便于精准追踪更新触发路径

## 优化改进
- **文档精简**: 删除过时的快速开始指南和 API 参考文档，减少维护负担

</details>
# v0.19.0 更新说明 (2026-07-14)

## 新增功能
- **自定义标题栏**: 实现自定义窗口标题栏，替换原生 Windows 窗口装饰，提供更精致的全平台一致体验
- **更新检测来源标记**: 新增更新检测来源选项，区分手动检查与自动检测，便于精准追踪更新触发路径

## 优化改进
- **文档精简**: 删除过时的快速开始指南和 API 参考文档，减少维护负担

---

# v0.18.0 Release Notes (2026-07-13)

## New Features
- **Plugin Category System**: Added `category` field; proxy-switch plugin categorized as `network-control`, laying the foundation for future plugin category filtering
- **Plugin Version History Enhancement**: Version history composable now prioritizes reading from standalone CHANGELOG.md files

## Bug Fixes
- **Search Bar Truncation Fix**: Fixed text truncation issue in the search bar across different viewport widths, improving responsive adaptation

## Improvements
- **proxy-switch Plugin Upgraded to v2.5.0**: Added global hotkeys, TCP request logging, dashboard navigation, traffic chain import/export, dynamic network interface listing; improved elevation communication mechanism and startup performance
- **CHANGELOG Generation Fix**: Fixed version sorting and date source logic in release.mjs to ensure correct semantic version ordering and accurate dates
- **Documentation Cleanup**: Removed outdated security authentication docs and search bar validation scripts, streamlining project documentation structure

<details>
<summary>中文说明</summary>

# v0.18.0 更新说明 (2026-07-13)

## 新增功能
- **插件分类系统**: 新增 `category` 字段，proxy-switch 插件归类为 `network-control`，为后续插件分类筛选奠定基础
- **插件版本历史增强**: 版本历史 composable 新增对插件独立 CHANGELOG.md 的优先读取支持

## 修复
- **搜索栏裁剪修复**: 修复搜索栏在不同视口宽度下的文字裁剪问题，提升响应式适配

## 优化改进
- **proxy-switch 插件升级至 v2.5.0**: 新增全局快捷键、TCP 请求日志、仪表盘导航、流量链导入导出、网络接口动态列表；优化提权通信机制和启动性能
- **CHANGELOG 生成修复**: 修复 release.mjs 中版本排序和日期来源逻辑，确保语义版本正确排序、日期准确
- **文档清理**: 删除过时的安全认证机制文档和搜索栏验证脚本，精简项目文档结构

</details>
# v0.18.0 更新说明 (2026-07-13)

## 新增功能
- **插件分类系统**: 新增 `category` 字段，proxy-switch 插件归类为 `network-control`，为后续插件分类筛选奠定基础
- **插件版本历史增强**: 版本历史 composable 新增对插件独立 CHANGELOG.md 的优先读取支持

## 修复
- **搜索栏裁剪修复**: 修复搜索栏在不同视口宽度下的文字裁剪问题，提升响应式适配

## 优化改进
- **proxy-switch 插件升级至 v2.5.0**: 新增全局快捷键、TCP 请求日志、仪表盘导航、流量链导入导出、网络接口动态列表；优化提权通信机制和启动性能
- **CHANGELOG 生成修复**: 修复 release.mjs 中版本排序和日期来源逻辑，确保语义版本正确排序、日期准确
- **文档清理**: 删除过时的安全认证机制文档和搜索栏验证脚本，精简项目文档结构

---

# v0.17.0 Release Notes (2026-07-13)

## New Features
- **Plugin Settings Default Path**: Plugin settings page now auto-fills default paths, improving configuration efficiency
- **Selective Plugin Release**: release.mjs now supports `--plugins` argument to build only specified plugins (e.g., `--plugins=proxy-switch`), skipping unchanged plugins and significantly reducing release time

## Bug Fixes
- **Grid Layout Overflow Fix**: Fixed horizontal overflow issue in homepage category grid layout and responsive breakpoint adaptation

## Improvements
- **Homepage Layout Optimization**: Optimized responsive layout logic for RecentTools and CategoryGrid components
- **Plugin Settings Enhancement**: Plugin settings composable now supports default path generation and auto-fill
- **Release Script Fix**: Fixed duplicate code block causing parse errors in release-with-sign.ps1
- **Release Script Enhancement**: release-with-sign.ps1 now supports -Plugins argument passthrough for end-to-end selective releases

<details>
<summary>中文说明</summary>

# v0.17.0 更新说明 (2026-07-13)

## 新增功能
- **插件设置默认路径填充**: 插件设置页面新增默认路径自动填充功能，提升配置效率
- **选择性插件发版**: release.mjs 新增 `--plugins` 参数，支持仅构建指定插件（如 `--plugins=proxy-switch`），跳过未变更的插件，大幅缩短发版时间

## 修复
- **网格布局溢出修复**: 修复首页分类网格布局水平溢出问题和响应式断点适配异常

## 优化改进
- **首页布局优化**: 优化 RecentTools 和 CategoryGrid 组件的响应式布局逻辑
- **插件设置增强**: 插件设置 composable 新增默认路径生成与填充机制
- **发版脚本修复**: 修复 release-with-sign.ps1 中重复代码块导致解析错误的问题
- **发版脚本增强**: release-with-sign.ps1 新增 -Plugins 参数透传，支持端到端选择性发版

</details>
# v0.17.0 更新说明 (2026-07-13)
## 新增功能
- **插件设置默认路径填充**: 插件设置页面新增默认路径自动填充功能，提升配置效率

## 修复
- **网格布局溢出修复**: 修复首页分类网格布局水平溢出问题和响应式断点适配异常

## 优化改进
- **首页布局优化**: 优化 RecentTools 和 CategoryGrid 组件的响应式布局逻辑
- **插件设置增强**: 插件设置 composable 新增默认路径生成与填充机制



## 新增功能
- **选择性插件发版**: release.mjs 新增 `--plugins` 参数，支持仅构建指定插件（如 `--plugins=proxy-switch`），跳过未变更的插件，大幅缩短发版时间

## 优化改进
- **发版脚本修复**: 修复 release-with-sign.ps1 中重复代码块导致解析错误的问题
- **发版脚本增强**: release-with-sign.ps1 新增 -Plugins 参数透传，支持端到端选择性发版

---

# v0.16.0 Release Notes (2026-07-13)

## New Features
- **Selective Plugin Release**: release.mjs now supports `--plugins` argument to build only specified plugins (e.g., `--plugins=proxy-switch`), skipping unchanged plugins and significantly reducing release time

## Improvements
- **Release Script Fix**: Fixed duplicate code block causing parse errors in release-with-sign.ps1
- **Release Script Enhancement**: release-with-sign.ps1 now supports -Plugins argument passthrough for end-to-end selective releases

<details>
<summary>中文说明</summary>

# v0.16.0 更新说明 (2026-07-13)

## 新增功能
- **选择性插件发版**: release.mjs 新增 `--plugins` 参数，支持仅构建指定插件（如 `--plugins=proxy-switch`），跳过未变更的插件，大幅缩短发版时间

## 优化改进
- **发版脚本修复**: 修复 release-with-sign.ps1 中重复代码块导致解析错误的问题
- **发版脚本增强**: release-with-sign.ps1 新增 -Plugins 参数透传，支持端到端选择性发版

</details>
# v0.16.0 更新说明 (2026-07-13)
## 新增功能
- **选择性插件发版**: release.mjs 新增 `--plugins` 参数，支持仅构建指定插件（如 `--plugins=proxy-switch`），跳过未变更的插件，大幅缩短发版时间

## 优化改进
- **发版脚本修复**: 修复 release-with-sign.ps1 中重复代码块导致解析错误的问题
- **发版脚本增强**: release-with-sign.ps1 新增 -Plugins 参数透传，支持端到端选择性发版

---

# v0.15.0 Release Notes (2026-06-22)

## Upgrades
- Rust toolchain upgraded to 1.96.0
- sysinfo 0.38 → 0.39 (system information)
- rusqlite 0.39 → 0.40 (SQLite database engine)
- windows crate 0.58 → 0.62 (Windows API bindings)
- Vite 7 → 8 (frontend build tool)
- TypeScript 5.7 → 6.0
- ESLint 9 → 10
- UnoCSS 66 → latest
- vue-tsc 2 → 3
- @types/node 24 → 26

## Plugin Dependency Upgrades
- proxy-switch: axum 0.7 → 0.8, ipstack 0.4 → 1.0

<details>
<summary>中文说明</summary>

# v0.15.0 更新说明 (2026-06-22)

## 升级

- Rust 工具链升级至 1.96.0
- sysinfo 0.38 → 0.39（系统信息获取）
- rusqlite 0.39 → 0.40（SQLite 数据库引擎）
- windows crate 0.58 → 0.62（Windows API 绑定）
- Vite 7 → 8（前端构建工具）
- TypeScript 5.7 → 6.0
- ESLint 9 → 10
- UnoCSS 66 → 最新
- vue-tsc 2 → 3
- @types/node 24 → 26

## 插件依赖升级

- proxy-switch: axum 0.7 → 0.8, ipstack 0.4 → 1.0

</details>
# v0.15.0 更新说明 (2026-06-22)
## 升级

- Rust 工具链升级至 1.96.0
- sysinfo 0.38 → 0.39（系统信息获取）
- rusqlite 0.39 → 0.40（SQLite 数据库引擎）
- windows crate 0.58 → 0.62（Windows API 绑定）
- Vite 7 → 8（前端构建工具）
- TypeScript 5.7 → 6.0
- ESLint 9 → 10
- UnoCSS 66 → 最新
- vue-tsc 2 → 3
- @types/node 24 → 26

## 插件依赖升级

- proxy-switch: axum 0.7 → 0.8, ipstack 0.4 → 1.0

---

# v0.14.0 Release Notes (2026-06-18)

## New Features
- Integrated Afdian payment system for plugin launch paywall and device code verification
- Added encrypted key-value storage (secure_store), replacing plaintext file storage to protect sensitive data
- Enhanced plugin security mechanism with device identification codes for sponsorship verification

## Refactoring
- Refactored plugin communication transport layer, optimized JSON-RPC error handling and timeout mechanisms
- Removed deprecated Tauri commands, streamlining backend API interface structure

## Documentation
- Updated AI development guidelines to v4.0, improving Qoder CN IDE configuration framework
- Added security and authentication mechanism documentation
- Updated project documentation structure and backend architecture docs

## Dependency Upgrades
- Upgraded project dependencies to latest versions, added TypeScript-related dependencies

<details>
<summary>中文说明</summary>

# v0.14.0 更新说明 (2026-06-18)

## 新功能
- 集成爱发电支付系统，实现插件启动付费拦截与设备码验证
- 新增加密键值存储（secure_store），替换明文文件存储，保护敏感数据
- 插件安全机制增强，新增设备识别码用于赞助验证

## 重构
- 重构插件通信传输层，优化 JSON-RPC 错误处理与超时机制
- 移除废弃的 Tauri 命令，精简后端 API 接口结构

## 文档
- 更新 AI 开发规范至 v4.0，完善 Qoder CN IDE 配置框架
- 新增安全与认证机制文档
- 更新项目文档结构和后端架构文档

## 依赖升级
- 升级项目依赖至最新版本，添加 TypeScript 相关依赖

</details>
# v0.14.0 更新说明 (2026-06-18)
## 新功能
- 集成爱发电支付系统，实现插件启动付费拦截与设备码验证
- 新增加密键值存储（secure_store），替换明文文件存储，保护敏感数据
- 插件安全机制增强，新增设备识别码用于赞助验证

## 重构
- 重构插件通信传输层，优化 JSON-RPC 错误处理与超时机制
- 移除废弃的 Tauri 命令，精简后端 API 接口结构

## 文档
- 更新 AI 开发规范至 v4.0，完善 Qoder CN IDE 配置框架
- 新增安全与认证机制文档
- 更新项目文档结构和后端架构文档

## 依赖升级
- 升级项目依赖至最新版本，添加 TypeScript 相关依赖


---

# v0.13.0 Release Notes (2026-06-17)

## New Features
- System tray menu now displays plugin quota indicator, showing current entitlements (unlimited plugins during trial period, max 3 for free tier after expiration)

<details>
<summary>中文说明</summary>

# v0.13.0 更新说明 (2026-06-17)

## 新功能
- 系统托盘菜单新增插件限额提示，直观显示当前使用权益（试用期内插件不限量，到期后免费版最多 3 个）

</details>

---

# v0.12.0 Release Notes (2026-06-16)

## New Features
- Added plugin count limit functionality (1 plugin in development environment, 3 in production)
- Added automatic plugin process cleanup on application exit, ensuring no orphan processes remain
- MSI installation now enforces administrator privileges to ensure sidecar plugin processes have sufficient system permissions

## Improvements
- Removed NSIS installer, unified to MSI as the sole installer format
- Simplified frontend update detection logic, unified to MSI update path
- Application exit now uses Windows Job Object as fallback for child process cleanup, preventing process leaks

<details>
<summary>中文说明</summary>

# v0.12.0 更新说明 (2026-06-16)

## 新功能
- 新增插件数量限制功能（开发环境 1 个，生产环境 3 个）
- 新增应用退出时插件进程自动清理机制，确保无残留孤儿进程
- MSI 安装后强制以管理员权限启动，确保 sidecar 插件进程有足够系统权限

## 优化
- 移除 NSIS 安装包，统一使用 MSI 作为唯一安装包格式
- 简化前端更新检测逻辑，统一走 MSI 更新路径
- 应用退出时通过 Windows Job Object 兜底清理子进程，防止进程泄露

</details>
# v0.12.0 更新说明 (2026-06-16)
## 新功能
- 新增插件数量限制功能（开发环境 1 个，生产环境 3 个）
- 新增应用退出时插件进程自动清理机制，确保无残留孤儿进程
- MSI 安装后强制以管理员权限启动，确保 sidecar 插件进程有足够系统权限

## 优化
- 移除 NSIS 安装包，统一使用 MSI 作为唯一安装包格式
- 简化前端更新检测逻辑，统一走 MSI 更新路径
- 应用退出时通过 Windows Job Object 兜底清理子进程，防止进程泄露

---

# v0.11.0 Release Notes (2026-06-16)

## New Features
- Added plugin launch paywall mechanism; unpaid users see a payment guidance dialog when launching plugins
- Upgraded device identification code algorithm, generating 32-bit SHA-256 digest from multi-source hardware fingerprints (CPU/motherboard/serial numbers)
- Support for precise navigation from payment gateway to the sponsorship verification section in settings

## Improvements
- Optimized payment dialog UI design following Apple HIG guidelines
- Improved trial period expiration and time rollback detection prompt text for clearer guidance
- Enhanced payment interception response parsing with JSON format support

<details>
<summary>中文说明</summary>

# v0.11.0 更新说明 (2026-06-16)

## 新功能
- 新增插件启动付费拦截机制，未赞助用户启动插件时弹出付费引导弹窗
- 升级设备识别码生成算法，基于多源硬件指纹（CPU/主板/序列号）生成 32 位 SHA-256 摘要
- 支持从支付网关精确跳转到设置页的赞助验证分区

## 优化
- 优化付费弹窗 UI 设计，遵循 Apple HIG 规范
- 优化试用期到期和时间回拨检测的提示文案，提供更清晰的操作指引
- 增强付费拦截响应解析，支持 JSON 格式

</details>
# v0.11.0 更新说明 (2026-06-16)
## 新功能
- 新增插件启动付费拦截机制，未赞助用户启动插件时弹出付费引导弹窗
- 升级设备识别码生成算法，基于多源硬件指纹（CPU/主板/序列号）生成 32 位 SHA-256 摘要
- 支持从支付网关精确跳转到设置页的赞助验证分区

## 优化
- 优化付费弹窗 UI 设计，遵循 Apple HIG 规范
- 优化试用期到期和时间回拨检测的提示文案，提供更清晰的操作指引
- 增强付费拦截响应解析，支持 JSON 格式

---

# v0.10.0 Release Notes (2026-06-15)

## New Features
- Added device identification code for sponsorship verification binding
- Added application single-instance lock to prevent duplicate launches
- Added Apple HIG-style header navigation design
- Log viewer now supports keyboard shortcuts (Ctrl+F search, Ctrl+E export, Space pause/resume)

## Improvements
- Redesigned update dialog with expand/collapse, ESC close, and background blur effects
- Optimized plugin version history fetching: prioritizes standalone CHANGELOG.md, falls back to ZIP extraction
- Plugin download repository README now includes version history link column
- Enhanced proxy-switch plugin rule management with rule testing and statistics reset
- Upgraded Vue, ESLint, Prettier and other core dependencies

## Bug Fixes
- Fixed grid layout horizontal overflow issue
- Fixed performance issue from repeated tray menu rebuilding
- Fixed plugin version history dialog not displaying remote new version content
- Fixed plugin upgrade download failure due to CORS restrictions

<details>
<summary>中文说明</summary>

# v0.10.0 更新说明 (2026-06-15)

## 新功能
- 新增设备识别码功能，用于赞助验证绑定
- 新增应用单实例锁定，防止重复启动
- 新增苹果 HIG 风格头部导航设计
- 日志查看器新增键盘快捷键支持（Ctrl+F 搜索、Ctrl+E 导出、Space 暂停/继续）

## 优化
- 重构版本更新弹窗，新增展开/折叠、ESC 关闭和背景模糊效果
- 插件版本历史获取机制优化：优先从独立 CHANGELOG.md 文件获取，回退到 ZIP 提取
- 插件下载仓库 README 增加版本历史链接列
- 代理切换插件规则管理功能增强，新增规则测试和统计重置
- 升级 Vue、ESLint、Prettier 等核心依赖

## 修复
- 修复网格布局水平溢出问题
- 修复托盘菜单重复重建导致的性能问题
- 修复插件版本历史弹窗无法显示远程新版本更新内容的问题
- 修复插件升级时因 CORS 限制导致下载失败的问题

</details>
# v0.10.0 更新说明 (2026-06-15)
## 新功能
- 新增设备识别码功能，用于赞助验证绑定
- 新增应用单实例锁定，防止重复启动
- 新增苹果 HIG 风格头部导航设计
- 日志查看器新增键盘快捷键支持（Ctrl+F 搜索、Ctrl+E 导出、Space 暂停/继续）

## 优化
- 重构版本更新弹窗，新增展开/折叠、ESC 关闭和背景模糊效果
- 插件版本历史获取机制优化：优先从独立 CHANGELOG.md 文件获取，回退到 ZIP 提取
- 插件下载仓库 README 增加版本历史链接列
- 代理切换插件规则管理功能增强，新增规则测试和统计重置
- 升级 Vue、ESLint、Prettier 等核心依赖

## 修复
- 修复网格布局水平溢出问题
- 修复托盘菜单重复重建导致的性能问题
- 修复插件版本历史弹窗无法显示远程新版本更新内容的问题
- 修复插件升级时因 CORS 限制导致下载失败的问题

---

# v0.9.1 Release Notes (2026-06-15)

## Improvements
- Optimized plugin version history fetching: prioritizes standalone CHANGELOG.md file (a few KB), falls back to ZIP extraction
- Enhanced publishing workflow: plugins now automatically generate standalone CHANGELOG.md files during release for in-app version history viewing
- Plugin download repository README now includes a version history link column

## Bug Fixes
- Fixed issue where plugin version history dialog could not display remote new version content
- Fixed plugin upgrade download failure due to CORS restrictions

<details>
<summary>中文说明</summary>

# v0.9.1 更新说明 (2026-06-15)

## 优化

- 插件版本历史获取机制优化：优先从独立 CHANGELOG.md 文件获取（几 KB），回退到 ZIP 提取
- 发布流程增强：插件发布时自动生成独立的 CHANGELOG.md 文件，供应用内版本历史查看
- 插件下载仓库 README 增加版本历史链接列

## 修复

- 修复插件版本历史弹窗中无法显示远程新版本更新内容的问题
- 修复插件升级时因 CORS 限制导致下载失败的问题

</details>
# v0.9.1 更新说明 (2026-06-15)
## 优化

- 插件版本历史获取机制优化：优先从独立 CHANGELOG.md 文件获取（几 KB），回退到 ZIP 提取
- 发布流程增强：插件发布时自动生成独立的 CHANGELOG.md 文件，供应用内版本历史查看
- 插件下载仓库 README 增加版本历史链接列

## 修复

- 修复插件版本历史弹窗中无法显示远程新版本更新内容的问题
- 修复插件升级时因 CORS 限制导致下载失败的问题

---

# v0.9.0 Release Notes (2026-06-14)

## New Features
- Added time-of-day distribution chart and usage habit insights
- Plugin upgrade UI now displays download progress and version diff details
- Plugin resource monitor table now features upgrade banner and quick upgrade entry

## Improvements
- Introduced Apple HIG design system, comprehensively redesigned plugin management UI visual style
- Unified theme color system to improve overall visual consistency
- Refactored plugin upgrade workflow with Rust-side ZIP download and progress monitoring
- Optimized table hover effects and card shadow styles

<details>
<summary>中文说明</summary>

# v0.9.0 更新说明 (2026-06-14)

## 新功能
- 新增时段分布图表和使用习惯洞察功能
- 插件升级界面增加下载进度显示和版本差异展示
- 插件资源监控表格新增升级提示横幅和快速升级入口

## 优化
- 引入 Apple HIG 设计系统，全面重构插件管理界面视觉风格
- 统一主题色彩系统，提升整体视觉一致性
- 重构插件升级流程，通过 Rust 端实现 ZIP 下载和进度监听
- 优化表格悬停效果和卡片阴影样式

</details>
# v0.9.0 更新说明 (2026-06-14)
## 新功能
- 新增时段分布图表和使用习惯洞察功能
- 插件升级界面增加下载进度显示和版本差异展示
- 插件资源监控表格新增升级提示横幅和快速升级入口

## 优化
- 引入 Apple HIG 设计系统，全面重构插件管理界面视觉风格
- 统一主题色彩系统，提升整体视觉一致性
- 重构插件升级流程，通过 Rust 端实现 ZIP 下载和进度监听
- 优化表格悬停效果和卡片阴影样式

---

# v0.8.0 Release Notes (2026-06-14)

## New Features
- Added system wakeup re-check: automatically checks for pending updates when the page becomes visible again
- Added exponential backoff retry strategy for update detection, up to 4 retries over ~3.5 minutes
- Added HTTP cache control mechanism to prevent CDN from serving stale data
- Added update dialog transition animation for improved user experience

## Bug Fixes
- Fixed missing 30-second retry mechanism after update detection polling failure
- Improved error handling and backoff mechanism in system status component

## Improvements
- Reduced update detection polling interval from 24 hours to 2 hours
- Optimized system status component styles to use theme variables for dark mode adaptation
- Completed update detection mechanism documentation and design specifications

<details>
<summary>中文说明</summary>

# v0.8.0 更新说明 (2026-06-14)

## 新功能
- 新增系统唤醒补检功能，页面重新可见时自动检查是否需要补检更新
- 新增升级检测指数退避重试策略，最多 4 次重试约 3.5 分钟
- 新增 HTTP 缓存控制机制，避免 CDN 返回过期数据
- 新增升级弹窗过渡动画，提升用户体验

## 修复
- 修复升级检测轮询失败后的 30 秒重试机制缺失问题
- 改进系统状态组件的错误处理和退避机制

## 优化
- 将升级检测定时轮询间隔从 24 小时缩短至 2 小时
- 优化系统状态组件样式使用主题变量适配暗色模式
- 完善升级检测机制相关文档和设计规范

</details>
# v0.8.0 更新说明 (2026-06-14)
## 新功能
- 新增系统唤醒补检功能，页面重新可见时自动检查是否需要补检更新
- 新增升级检测指数退避重试策略，最多 4 次重试约 3.5 分钟
- 新增 HTTP 缓存控制机制，避免 CDN 返回过期数据
- 新增升级弹窗过渡动画，提升用户体验

## 修复
- 修复升级检测轮询失败后的 30 秒重试机制缺失问题
- 改进系统状态组件的错误处理和退避机制

## 优化
- 将升级检测定时轮询间隔从 24 小时缩短至 2 小时
- 优化系统状态组件样式使用主题变量适配暗色模式
- 完善升级检测机制相关文档和设计规范

---

# v0.7.0 Release Notes (2026-06-14)

## New Features
- Added local usage statistics, supporting tool usage duration and frequency tracking
- Added dynamic height adaptation for resource monitor table, improving data browsing experience
- Added CHANGELOG.md copy functionality in plugin build scripts, ensuring plugin packages include update logs

## Bug Fixes
- Fixed plugin management page layout and button display issues

## Improvements
- Redesigned settings page to card-based layout with new feature modules, improving visual hierarchy and interaction
- Redesigned plugin settings page UI to card-based layout, unifying design style
- Refactored plugin logs and resource monitor components, optimizing component architecture and performance
- Updated project specification document architecture, improving development standards

<details>
<summary>中文说明</summary>

# v0.7.0 更新说明 (2026-06-14)

## 新功能
- 新增本地使用统计功能，支持查看工具使用时长和频率
- 新增资源监控表格动态高度适配，提升数据浏览体验
- 新增插件构建脚本 CHANGELOG.md 复制功能，确保插件包包含更新日志

## 修复
- 修复插件管理页面布局和按钮显示问题

## 优化
- 重构设置页面为卡片化布局，新增功能模块，提升视觉层次和交互体验
- 重构插件设置页面 UI 为卡片化布局，统一设计风格
- 重构插件日志和资源监控组件，优化组件架构和性能
- 更新项目规范文档架构，完善开发规范体系

</details>
# v0.7.0 更新说明 (2026-06-14)
## 新功能
- 新增本地使用统计功能，支持查看工具使用时长和频率
- 新增资源监控表格动态高度适配，提升数据浏览体验
- 新增插件构建脚本 CHANGELOG.md 复制功能，确保插件包包含更新日志

## 修复
- 修复插件管理页面布局和按钮显示问题

## 优化
- 重构设置页面为卡片化布局，新增功能模块，提升视觉层次和交互体验
- 重构插件设置页面 UI 为卡片化布局，统一设计风格
- 重构插件日志和资源监控组件，优化组件架构和性能
- 更新项目规范文档架构，完善开发规范体系

---

# v0.6.0 Release Notes (2026-06-13)

## New Features
- Added Afdian payment verification, supporting payment verification through the Afdian platform
- Added global payment verification intercept dialog; unverified users are automatically prompted
- Added Afdian configuration module in settings page for configuring verification parameters
- Refactored bottom status bar component architecture, splitting into independent status components
- Added SystemStatusWidget for displaying system information independently
- Added VersionHistoryPopover component for viewing version update records

## Bug Fixes
- Fixed payment verification dialog logic for correct handling of various expiration scenarios
- Fixed edge cases in plugin lifecycle management
- Fixed style and functional compatibility issues after settings page component splitting

## Improvements
- Refactored bottom status bar component architecture, improving code maintainability
- Refactored plugin management commands, optimizing plugin install and update workflows
- Updated project configuration and development tool definitions
- Updated dependency versions for improved overall stability

<details>
<summary>中文说明</summary>

# v0.6.0 更新说明 (2026-06-13)

## 新功能
- 新增爱发电付费验证功能，支持通过爱发电平台进行付费验证
- 新增付费验证全局拦截弹窗，未验证用户使用时自动弹出提示
- 新增设置页面爱发电配置模块，可配置验证参数
- 新增底部状态栏组件架构重构，拆分为独立的状态组件
- 新增系统状态小组件（SystemStatusWidget），独立显示系统信息
- 新增版本历史弹窗组件（VersionHistoryPopover），可查看版本更新记录

## 修复
- 修复付费验证弹窗逻辑，支持多种过期场景的正确处理
- 修复插件生命周期管理中的边界问题
- 修复设置页面组件拆分后的样式和功能兼容问题

## 优化
- 底部状态栏组件架构重构，提升代码可维护性
- 插件管理命令重构，优化插件安装和更新流程
- 项目配置和开发工具定义更新
- 依赖包版本更新，提升整体稳定性

</details>
# v0.6.0 更新说明 (2026-06-13)
## 新功能
- 新增爱发电付费验证功能，支持通过爱发电平台进行付费验证
- 新增付费验证全局拦截弹窗，未验证用户使用时自动弹出提示
- 新增设置页面爱发电配置模块，可配置验证参数
- 新增底部状态栏组件架构重构，拆分为独立的状态组件
- 新增系统状态小组件（SystemStatusWidget），独立显示系统信息
- 新增版本历史弹窗组件（VersionHistoryPopover），可查看版本更新记录

## 修复
- 修复付费验证弹窗逻辑，支持多种过期场景的正确处理
- 修复插件生命周期管理中的边界问题
- 修复设置页面组件拆分后的样式和功能兼容问题

## 优化
- 底部状态栏组件架构重构，提升代码可维护性
- 插件管理命令重构，优化插件安装和更新流程
- 项目配置和开发工具定义更新
- 依赖包版本更新，提升整体稳定性

---

# v0.5.0 Release Notes (2026-06-10)

## New Features
- Proxy-switch plugin TUN 2.0 full rewrite, supporting IPv6, DNS forwarding, and automatic adapter management
- Added traffic chain management: create, edit, import/export traffic chains
- Added rule tags and filtering for quick proxy rule location and management
- Added node connection testing for visual connectivity status
- Added global hotkey configuration for quick proxy switching
- Added TCP request logging with pagination and auto-refresh
- Added plugin administrator elevation mechanism for plugins requiring admin privileges
- Added plugin version history for viewing and rolling back plugin versions
- Added WinTun driver management with automatic detection and installation

## Bug Fixes
- Fixed TUN adapter lifecycle management issues, improving connection stability
- Fixed DNS forwarding bypassing local DNS
- Fixed edge cases in TCP stream processing and DNS queries
- Fixed configuration file write safety with atomic writes to prevent corruption

## Improvements
- Optimized logging system performance, reducing resource usage
- Enhanced plugin communication pipeline security
- Improved form control styles in dark mode
- Updated dashboard UI with rule navigation and quick jump support
- Updated dependency versions for improved overall stability

<details>
<summary>中文说明</summary>

# v0.5.0 更新说明 (2026-06-10)

## 新功能
- 代理切换插件 TUN 2.0 全新重构，支持 IPv6、DNS 转发与自动适配器管理
- 新增流量链管理功能，支持创建、编辑、导入导出流量链
- 新增规则标签和筛选功能，方便快速定位和管理代理规则
- 新增节点连接测试功能，直观显示节点连通状态
- 新增全局快捷键配置，可通过快捷键快速切换代理
- 新增 TCP 请求日志，支持分页浏览和自动刷新
- 新增插件管理员提权机制，需要管理员权限的插件可安全提权运行
- 新增插件版本历史功能，可查看和回退插件版本
- 新增 WinTun 驱动管理功能，自动检测和安装驱动

## 修复
- 修复 TUN 适配器生命周期管理问题，提升连接稳定性
- 修复 DNS 转发绕过本地 DNS 的问题
- 修复 TCP 流处理和 DNS 查询中的边界问题
- 修复配置文件写入安全性问题，采用原子写入防止损坏

## 优化
- 日志系统性能优化，降低资源占用
- 插件通信管道安全性增强
- 暗色模式下表单控件样式优化
- 仪表盘界面更新，支持规则导航和快速跳转
- 依赖包版本更新，提升整体稳定性

</details>
# v0.5.0 更新说明 (2026-06-10)
## 新功能
- 代理切换插件 TUN 2.0 全新重构，支持 IPv6、DNS 转发与自动适配器管理
- 新增流量链管理功能，支持创建、编辑、导入导出流量链
- 新增规则标签和筛选功能，方便快速定位和管理代理规则
- 新增节点连接测试功能，直观显示节点连通状态
- 新增全局快捷键配置，可通过快捷键快速切换代理
- 新增 TCP 请求日志，支持分页浏览和自动刷新
- 新增插件管理员提权机制，需要管理员权限的插件可安全提权运行
- 新增插件版本历史功能，可查看和回退插件版本
- 新增 WinTun 驱动管理功能，自动检测和安装驱动

## 修复
- 修复 TUN 适配器生命周期管理问题，提升连接稳定性
- 修复 DNS 转发绕过本地 DNS 的问题
- 修复 TCP 流处理和 DNS 查询中的边界问题
- 修复配置文件写入安全性问题，采用原子写入防止损坏

## 优化
- 日志系统性能优化，降低资源占用
- 插件通信管道安全性增强
- 暗色模式下表单控件样式优化
- 仪表盘界面更新，支持规则导航和快速跳转
- 依赖包版本更新，提升整体稳定性

---

# v0.4.0 Release Notes (2026-05-01)

## New Features
- Homepage tool cards now support multiple display modes with switchable views and active mode highlighting
- Notification sound feature with multiple sound styles and volume control; different events play different sound effects
- Performance settings now include system status refresh interval configuration (1-30 seconds adjustable)

<details>
<summary>中文说明</summary>

# v0.4.0 更新说明 (2026-05-01)

## 新功能
- 首页工具卡片支持多显示模式，可切换不同视图并高亮当前激活模式
- 通知声音功能，支持多种声音风格和音量调节，不同事件播放不同音效
- 性能设置新增系统状态刷新间隔配置（1-30 秒可调）

</details>
# v0.4.0 更新说明 (2026-05-01)
## 新功能
- 首页工具卡片支持多显示模式，可切换不同视图并高亮当前激活模式
- 通知声音功能，支持多种声音风格和音量调节，不同事件播放不同音效
- 性能设置新增系统状态刷新间隔配置（1-30 秒可调）

---

# v0.3.7 Release Notes (2026-04-30)

## New Features
- Health monitoring now uses consecutive heartbeat stability threshold; auto-resets restart count after sustained stability
- Resource polling adds independent health status polling, updating plugin health every 3 seconds
- Production environment now captures frontend logs, improving troubleshooting efficiency

## Bug Fixes
- Fixed issue where plugins disabled by users were still auto-restarted by health monitoring
- Fixed toggle state desync when plugins were disabled due to excessive restarts
- Fixed network detection error on systems without WiFi modules
- Fixed iframe resource path resolution in PluginFrame component production mode

## Improvements
- Rust sidecar plugins now uniformly enable static-linked MSVC runtime, no longer requiring VC++ Redistributable
- Hidden sidecar console windows on Windows to prevent CMD window popups
- Plugin management page tabs redesigned as custom pill-style for more compact layout
- Watchdog now logs enhanced crash information with exit code descriptions
- Pomodoro plugin release build enables LTO and extreme size optimization

<details>
<summary>中文说明</summary>

# v0.3.7 更新说明 (2026-04-30)

## 新功能
- 健康监控引入连续心跳稳定阈值，连续稳定后自动重置重启计数
- 资源轮询新增独立健康状态轮询，每 3 秒更新插件健康状态
- 生产环境新增前端日志捕获功能，提升问题排查效率

## 修复
- 修复插件被用户手动禁用后仍被健康监控自动重启的问题
- 修复插件重启次数过多被禁用时，前端开关状态不同步的问题
- 修复无 WiFi 模块的系统下代理插件网络检测报错的问题
- 修复 PluginFrame 组件生产模式下 iframe 资源路径解析问题

## 优化
- Rust sidecar 插件统一启用静态链接 MSVC 运行时，不再依赖 VC++ Redistributable
- Windows 下隐藏 sidecar 控制台窗口，避免弹出 CMD 窗口影响体验
- 插件管理页面标签页改为自定义 pill 形态，布局更紧凑
- 插件崩溃时看门狗增强崩溃信息记录，支持退出码描述
- Pomodoro 插件 release 构建启用 LTO 和极致体积优化

</details>
# v0.3.7 更新说明 (2026-04-30)
## 新功能
- 健康监控引入连续心跳稳定阈值，连续稳定后自动重置重启计数
- 资源轮询新增独立健康状态轮询，每 3 秒更新插件健康状态
- 生产环境新增前端日志捕获功能，提升问题排查效率

## 修复
- 修复插件被用户手动禁用后仍被健康监控自动重启的问题
- 修复插件重启次数过多被禁用时，前端开关状态不同步的问题
- 修复无 WiFi 模块的系统下代理插件网络检测报错的问题
- 修复 PluginFrame 组件生产模式下 iframe 资源路径解析问题

## 优化
- Rust sidecar 插件统一启用静态链接 MSVC 运行时，不再依赖 VC++ Redistributable
- Windows 下隐藏 sidecar 控制台窗口，避免弹出 CMD 窗口影响体验
- 插件管理页面标签页改为自定义 pill 形态，布局更紧凑
- 插件崩溃时看门狗增强崩溃信息记录，支持退出码描述
- Pomodoro 插件 release 构建启用 LTO 和极致体积优化

---

# v0.3.6 Release Notes (2026-04-29)

## New Features
- Improved production logging system with frontend log capture for easier troubleshooting

<details>
<summary>中文说明</summary>

# v0.3.6 更新说明 (2026-04-29)

## 新功能
- 完善生产环境日志系统，新增前端日志捕获功能，方便排查问题

</details>

---

# v0.3.5 Release Notes (2026-04-29)

## New Features
- Bottom version number popup now includes version history viewing for quick access to past update content

<details>
<summary>中文说明</summary>

# v0.3.5 更新说明 (2026-04-29)

## 新功能
- 底部版本号弹窗新增版本历史查看功能，可快速了解历次更新内容

</details>

---

# v0.3.2 Release Notes (2026-04-28)

## New Features
- Added proxy-switch plugin for system-level proxy management with multi-profile switching
- Pomodoro plugin upgraded to v2.0, supporting light/dark themes and hotkeys
- Implemented plugin auto-start mechanism for boot-time automatic plugin execution
- Added global hotkey settings with capture, display, and save support
- Added network environment detection with WiFi SSID identification
- System tray now includes "Check for Updates" menu item with version update status
- Update detection system supports automatic MSI/NSIS installer type matching
- Bottom version number shows pulse indicator when update is available
- Auto-push system notifications for plugin crash/restart/install/uninstall events
- Homepage cards support drag-and-drop reordering within categories

## Bug Fixes
- Fixed auto-check-update setting not persisting
- Fixed desync between notification popup and tray status
- Fixed rule editing and log table rendering anomalies

## Improvements
- Refactored proxy-switch main UI to thin-shell layout with clearer component structure
- Optimized sidebar toggle with manual hide and state persistence
- Removed unused @tauri-apps/plugin-sql dependency to reduce bundle size
- Extracted timeout execution logic, optimizing plugin management command implementation
- Multiple code standard and UI detail improvements

<details>
<summary>中文说明</summary>

# v0.3.2 更新说明 (2026-04-28)

## 新功能
- 新增代理切换插件，支持系统级代理管理与多 Profile 切换
- 番茄钟插件升级至 v2.0，支持亮暗色主题与快捷键
- 实现插件自启动机制，支持开机自动运行指定插件
- 新增全局快捷键设置功能，支持捕获、显示与保存快捷键
- 新增网络环境检测功能，支持 WiFi SSID 识别
- 系统托盘新增「检查更新」菜单项，支持版本更新状态展示
- 升级检测系统支持 MSI/NSIS 安装类型自动匹配
- 底部版本号更新时显示脉冲指示器，增强更新感知
- 插件崩溃/重启/安装/卸载时自动推送系统通知
- 首页卡片支持同分类内拖拽排序，归类更便捷

## 修复
- 修复自动检查更新设置无法持久化的问题
- 修复通知弹窗与托盘状态不同步的问题
- 修复规则编辑与日志表格渲染异常

## 优化
- 代理切换主界面重构为薄壳布局，组件化结构更清晰
- 侧边栏显隐切换功能优化，支持手动隐藏与状态持久化
- 移除未使用的 @tauri-apps/plugin-sql 依赖，降低包体积
- 提取超时执行逻辑，优化插件管理命令实现
- 代码规范与界面细节多项优化

</details>
# v0.3.2 更新说明 (2026-04-28)

## 新功能
- 新增代理切换插件，支持系统级代理管理与多 Profile 切换
- 番茄钟插件升级至 v2.0，支持亮暗色主题与快捷键
- 实现插件自启动机制，支持开机自动运行指定插件
- 新增全局快捷键设置功能，支持捕获、显示与保存快捷键
- 新增网络环境检测功能，支持 WiFi SSID 识别
- 系统托盘新增「检查更新」菜单项，支持版本更新状态展示
- 升级检测系统支持 MSI/NSIS 安装类型自动匹配
- 底部版本号更新时显示脉冲指示器，增强更新感知
- 插件崩溃/重启/安装/卸载时自动推送系统通知
- 首页卡片支持同分类内拖拽排序，归类更便捷

## 修复
- 修复自动检查更新设置无法持久化的问题
- 修复通知弹窗与托盘状态不同步的问题
- 修复规则编辑与日志表格渲染异常

## 优化
- 代理切换主界面重构为薄壳布局，组件化结构更清晰
- 侧边栏显隐切换功能优化，支持手动隐藏与状态持久化
- 移除未使用的 @tauri-apps/plugin-sql 依赖，降低包体积
- 提取超时执行逻辑，优化插件管理命令实现
- 代码规范与界面细节多项优化

---

<details>
<summary>中文说明</summary>

# 更新日志

> 所有版本更新记录。最新版本在最前面。

</details>
