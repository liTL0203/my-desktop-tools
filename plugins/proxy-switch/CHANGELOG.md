# v2.6.0 Release Notes (2026-07-14)

## New Features
- **Internationalization**: Plugin name and UI text now support automatic Chinese/English switching, following the core application language setting

## Improvements
- **Settings Architecture**: Extracted plugin settings update logic into standalone functions, improving maintainability

<details>
<summary>中文说明</summary>

# v2.6.0 更新说明 (2026-07-14)

## 新增功能
- **国际化支持**: 插件名称和界面文案支持中英文自动切换，跟随核心程序语言设置

## 优化改进
- **设置架构**: 插件设置更新逻辑提取为独立函数，提升可维护性

</details>

---

# v2.5.0 Release Notes (2026-07-12)

## New Features
- **Global Hotkey Configuration**: Quick proxy toggle via hotkeys, with new RPC interface
- **DNS Settings Panel**: Complete DNS settings and cache management UI for visual management of DNS cache entries
- **TCP Request Logging**: New TCP request log panel with pagination and auto-refresh auto-scroll
- **Dashboard Navigation**: Dashboard UI refactor with rule navigation and quick jump
- **Traffic Chain Import/Export**: Import/export support for traffic chain configurations
- **Dynamic Network Interface List**: Node management replaces hardcoded dropdown with dynamic system network interface detection

## Improvements
- **Elevation Communication Simplification**: Simplified plugin elevation communication mechanism, reducing architectural complexity
- **Startup Performance**: Optimized plugin startup flow, improving launch speed
- **Driver Management**: Improved driver directory opening and status detection logic
- **Dependency Upgrades**: axum 0.7 → 0.8, ipstack 0.4 → 1.0

<details>
<summary>中文说明</summary>

# v2.5.0 更新说明 (2026-07-12)

## 新增功能
- **全局快捷键配置**: 支持通过快捷键快速切换代理开关，新增 RPC 接口
- **DNS 设置面板**: 完成 DNS 设置及缓存管理 UI，支持可视化管理 DNS 缓存条目
- **TCP 请求日志**: 新增 TCP 请求日志面板，支持分页浏览和自动刷新自动滚动
- **仪表盘导航**: 仪表盘界面重构，新增规则导航和快速跳转功能
- **流量链导入导出**: 支持流量链配置的导入导出功能
- **网络接口动态列表**: 节点管理中替换硬编码下拉框，动态获取系统网络接口列表

## 优化改进
- **提权通信简化**: 简化插件提权通信机制，降低架构复杂度
- **启动性能优化**: 优化插件启动流程，提升启动速度
- **驱动管理增强**: 优化驱动目录打开和状态检测逻辑
- **依赖升级**: axum 0.7 → 0.8, ipstack 0.4 → 1.0

</details>

---

# v2.4.0 Release Notes (2026-06-06)

## Bug Fixes
- TUN adapter lifecycle deep fix: resolved adapter deletion on plugin close
  - Root cause: wintun's `WintunCloseAdapter` removes the adapter created by `WintunCreateAdapter`; cannot persist across processes
  - Fix: Use fixed GUID for adapter creation; Windows remembers IP config by GUID; rebuild via same GUID on each enable (open if exists, create if not)
  - `shutdown()` proactively releases adapter handle; `resume()` rebuilds adapter via fixed GUID and checks if IP auto-recovered
  - `cmd_delete_tun_adapter` simplified to drop TunRuntime (wintun auto-removes)
  - Added `TUN_ADAPTER_GUID` fixed constant for consistent adapter identity and IP config across restarts

<details>
<summary>中文说明</summary>

# v2.4.0 更新说明 (2026-06-06)

## Bug 修复
- TUN 适配器生命周期深度修复：解决插件关闭时适配器被删除的问题
  - 深层根因：wintun 设计中 `WintunCloseAdapter` 会移除 `WintunCreateAdapter` 创建的适配器，无法跨进程持久化
  - 修复：使用固定 GUID 创建适配器，Windows 按 GUID 记忆 IP 配置，每次启用时通过相同 GUID 重建（存在则打开，不存在则创建）
  - `shutdown()` 主动释放适配器句柄，`resume()` 通过固定 GUID 重建适配器并检查 IP 是否已自动恢复
  - `cmd_delete_tun_adapter` 简化为丢弃 TunRuntime（wintun 自动移除）
  - 新增 `TUN_ADAPTER_GUID` 固定常量，确保适配器身份和 IP 配置跨重启一致

</details>

---

# v2.3.0 Release Notes (2026-06-06)

## Bug Fixes
- TUN adapter lifecycle fix (initial): Added `TunRuntime::disable()` / `resume()` methods
  - Root cause: `*tun = None` in `disable_proxy_background` triggers Arc cascade drop
  - `cmd_enable_proxy` detects disabled TunRuntime and calls resume to reuse
  - Extracted `spawn_accept_loop` common function; start/resume share accept loop logic

<details>
<summary>中文说明</summary>

# v2.3.0 更新说明 (2026-06-06)

## Bug 修复
- TUN 适配器生命周期修复（初版）：新增 `TunRuntime::disable()` / `resume()` 方法
  - 根因：`disable_proxy_background` 中 `*tun = None` 触发 Arc 级联 drop
  - `cmd_enable_proxy` 支持检测已禁用的 TunRuntime 并调用 resume 复用
  - 抽取 `spawn_accept_loop` 公共函数，start/resume 共享接受循环逻辑

</details>

---

# v2.2.0 Release Notes (2026-05-25)

## New Features
- **Traffic Chain Management**: Create, edit, import/export traffic chains supporting multi-level proxy chaining
- **Rule Tag System**: Rule tags and filtering for quick proxy rule location and management
- **Node Connection Testing**: Visual node connectivity status
- **Traffic Chain Health Monitoring**: Real-time link availability health checks
- **TUN 2.0 Rule Refactor**: Designed and implemented rule engine refactoring for enhanced rule matching flexibility

<details>
<summary>中文说明</summary>

# v2.2.0 更新说明 (2026-05-25)

## 新增功能
- **流量链管理**: 实现流量链的创建、编辑、导入导出功能，支持多级代理串联
- **规则标签系统**: 新增规则标签和筛选功能，方便快速定位和管理代理规则
- **节点连接测试**: 新增节点连接测试功能，直观显示节点连通状态
- **流量链健康监控**: 新增流量链健康检查机制，实时检测链路可用性
- **TUN 2.0 规则重构**: 设计并实现规则引擎重构方案，增强规则匹配灵活性

</details>

---

# v2.1.0 Release Notes (2026-05-23)

## New Features
- **TLS SNI Domain Extraction**: When DNS misses, extracts target domain via TLS ClientHello parsing and writes back to DNS cache
- **IPv6 TUN Support**: Complete IPv6 traffic support in TUN mode

## Improvements
- Cache physical NIC IPv6 addresses for improved DNS forwarding performance
- Optimized IPv6 support and DNS query parsing (compression pointer 0xC0 support)
- Resolved multi-interface DNS bypassing local DNS issue
- OnceLock cache made resettable for network change refresh

<details>
<summary>中文说明</summary>

# v2.1.0 更新说明 (2026-05-23)

## 新增功能
- **TLS SNI 域名提取**: DNS 未命中时通过解析 TLS ClientHello 提取目标域名，回写 DNS 缓存
- **IPv6 TUN 支持**: 完成 TUN 模式对 IPv6 流量的完整支持

## 优化改进
- 缓存物理网卡 IPv6 地址提升 DNS 转发性能
- 优化 IPv6 支持、DNS 查询解析（支持压缩指针 0xC0）
- 解决多接口 DNS 绕过本地 DNS 的问题
- OnceLock 缓存改为可重置，支持网络变更时刷新

</details>

---

# v2.0.0 Release Notes (2026-06-05)

## Refactoring
- Refactored from system proxy mode to TUN mode (virtual NIC traffic interception)
- 100% global traffic interception, covering apps that bypass system proxy (games, CLI tools, etc.)

## New Features
- TUN virtual NIC management (based on WinTun driver)
- Traffic chains (multi-level proxy chaining)
- Local DNS server (127.0.0.1:53) + DNS relay + DNS hijack + persistent cache
- DNS cache management RPC interface (list/clear/delete/update)
- WinTun driver one-click install/update/uninstall/version detection
- Node management (HTTP/SOCKS5/VPN/chain proxy)
- Rule engine upgrade (domain suffix, keyword, port, protocol, process matching)
- Dashboard status monitoring
- Rule import/export (AutoProxy/SwitchyOmega/plaintext)

## Removed
- Removed legacy system proxy mode (only modified WinInet settings)
- Dead code cleanup (~2860 lines, 6 files)

## Security Fixes
- Named pipe access control: NULL DACL replaced with Authenticated Users + SYSTEM DACL to prevent arbitrary process connecting to elevated sidecar
- URL open command injection prevention: Only http/https protocols allowed, using ShellExecuteW instead of cmd /c start
- Security descriptor memory leak fix: Box::leak replaced with PipeSecurity struct holding ownership

## Bug Fixes
- IPv6 route recovery fully implemented (restore backed-up routes instead of just deleting default route)
- IPv6 routing table independent parsing logic (no subnet mask format)
- OnceLock cache made resettable (DNS address + physical NIC IP/index, supporting network change refresh)
- Fake IP allocation conflict detection (253 iterations to avoid IP reuse conflicts)
- Atomic config file writes (write .tmp then rename; crash won't corrupt file)
- save_config field handling clarified (enabled/dns managed by independent RPC)

## Robustness Enhancements
- DNS relay retry mechanism (retry once after 3s timeout)
- HTTP CONNECT response parsing: Parse HTTP status line to extract status code, replacing loose string matching
- SOCKS5 proxy: Support RFC 1929 Username/Password authentication + IPv6 address support
- DNS query parsing supports compression pointer (0xC0)
- DNS response parsing adds bounds checking and label length validation

<details>
<summary>中文说明</summary>

# v2.0.0 更新说明 (2026-06-05)

## 重构
- 从系统代理模式重构为 TUN 模式（虚拟网卡拦截）
- 100% 全局流量劫持，覆盖不走系统代理的程序（游戏、CLI 工具等）

## 新增
- TUN 虚拟网卡管理（基于 WinTun 驱动）
- 流量链功能（多级代理串联）
- 本地 DNS 服务器 (127.0.0.1:53) + DNS 中继 + DNS 劫持 + 持久化缓存
- DNS 缓存管理 RPC 接口（list/clear/delete/update）
- WinTun 驱动一键安装/更新/卸载/版本检测
- 节点管理（HTTP/SOCKS5/VPN/链式代理）
- 规则引擎升级（域名后缀、关键词、端口、协议、进程匹配）
- 仪表盘状态监控
- 规则导入/导出（AutoProxy/SwitchyOmega/纯文本）

## 移除
- 移除旧版系统代理模式（仅修改 WinInet 设置）
- 死代码清理（~2860 行，6 个文件）

## 安全修复
- 命名管道访问权限：NULL DACL 替换为 Authenticated Users + SYSTEM DACL，防止任意进程连接提权 sidecar
- URL 打开命令注入防护：仅允许 http/https 协议，使用 ShellExecuteW 替代 cmd /c start
- 安全描述符内存泄漏修复：Box::leak 替换为 PipeSecurity 结构体持有所有权

## Bug 修复
- IPv6 路由恢复完整实现（恢复备份路由而非仅删除默认路由）
- IPv6 路由表独立解析逻辑（无子网掩码格式）
- OnceLock 缓存改为可重置（DNS 地址 + 物理网卡 IP/索引，支持网络变更时刷新）
- 假 IP 分配冲突检测（253 次循环避免 IP 复用冲突）
- 配置文件原子写入（先写 .tmp 再 rename，崩溃不损坏文件）
- save_config 字段处理明确化（enabled/dns 由独立 RPC 管理）

## 健壮性增强
- DNS relay 重试机制（3s 超时后重试一次）
- HTTP CONNECT 响应解析：解析 HTTP 状态行提取状态码，替代宽松字符串匹配
- SOCKS5 代理：支持 RFC 1929 Username/Password 认证 + IPv6 地址支持
- DNS 查询解析支持压缩指针 (0xC0)
- DNS 响应解析增加边界检查和标签长度校验

</details>

---

# v1.2.0 Release Notes (2026-05-05)

## New Features
- Auto rule switching
- Multi-profile management
- Auto-start support

## Improvements
- Optimized proxy detection speed
- Improved system tray interaction

## Bug Fixes
- Fixed Windows proxy setting failure

<details>
<summary>中文说明</summary>

# v1.2.0 更新说明 (2026-05-05)

## 新增
- 支持规则自动切换
- 多 Profile 管理
- 自动启动功能

## 优化
- 优化代理检测速度
- 改进系统托盘交互

## 修复
- 修复 Windows 代理设置失败问题

</details>

---

# v1.1.0 Release Notes (2026-04-15)

## New Features
- System-level proxy management
- Proxy rule configuration

<details>
<summary>中文说明</summary>

# v1.1.0 更新说明 (2026-04-15)

## 新增
- 系统级代理管理
- 代理规则配置

</details>

---

# v1.0.0 Release Notes (2026-04-01)

## New Features
- Initial release
- Basic proxy switching functionality

<details>
<summary>中文说明</summary>

# v1.0.0 更新说明 (2026-04-01)

## 新增
- 初始版本
- 基础代理切换功能

</details>
