# v3.1.1 Release Notes (2026-08-27)

## Improvements
- **SettingsTab Layout**: Added component inner padding to improve visual spacing and readability of the settings page

<details>
<summary>中文说明</summary>

# v3.1.1 更新说明 (2026-08-27)

## 改进
- **设置页布局**：为设置页组件添加内边距，改善视觉间距与可读性

</details>

---

# v3.1.0 Release Notes (2026-08-27)

## Maintenance
- Version sync release: minor-version milestone; no functional changes since v3.0.4

<details>
<summary>中文说明</summary>

# v3.1.0 更新说明 (2026-08-27)

## 维护
- 版本同步发布：次版本号里程碑；自 v3.0.4 以来无功能性变更

</details>

---

# v3.0.4 Release Notes (2026-08-27)

## Patch: Node-Test Parity with Data Plane for Interface-Egress Nodes

### Fixed
- **Node test reported offline while actual traffic worked** (three stacked root causes, all fixed):
  1. **Missing test-time interface route**: the L1-interface /32 route (needed because split-tunnel VPN interfaces have no route covering the proxy server IP, making `IP_UNICAST_IF`-bound connects fail with `WSAEENETUNREACH`) was only completed at TUN **enable** time and removed on disable — so testing while TUN was off always failed. The test now completes the same route itself (temporary `RouteManager`, added before and removed after the probe; skipped when TUN is running since the enable-time route already exists).
  2. **Probe target rejected by policy proxies**: the HTTP probe's `CONNECT connect-timeout.mozilla.org` got `403` from corporate proxies that only whitelist business domains — killing the verdict even though the proxy was fully alive. Any well-formed HTTP status line from the proxy now counts as **node online** (200 → "CONNECT 成功"; other 3-digit codes → "代理在线，探针目标可能被策略限制，不影响实际使用"); only no-response / non-HTTP fails.
  3. Environment note: a stale `target\debug` sidecar (without the `Get-NetIPInterface` fallback for ras VPN adapters that never appear in `Get-NetAdapter`) was still being launched by the Core watchdog; deployment now puts the release build at the plugin root (scanner's first-priority path).
- **Timeout 5s → 10s**: the first probe includes cold-cache PowerShell lookups (interface index + route table) of ~3-5s.
- **Failure reason now visible**: the node card's status dot / text shows the backend `detail` as a tooltip (interface unreachable vs proxy handshake failure vs timeout), instead of a bare "不可用".

---

# v3.0.3 Release Notes (2026-08-27)

## Patch: Stale TUN Device Auto-Heal on Adapter Creation

### Fixed
- **Auto-heal for stale wintun SWD device nodes**: when a previous sidecar process was force-killed, its `SWD\WINTUN\{fixed-GUID}` device node could linger in a half-dead state (present in PnP, dead at the interface layer), making every subsequent `WintunCreateAdapter` with the fixed GUID fail with `ERROR_ALREADY_EXISTS` — the user saw "启用失败: 启动 TUN 失败: 创建适配器失败: Failed to create adapter" forever until manual cleanup. Adapter creation now self-heals: on create failure, the plugin enumerates present net-class devices, removes **exactly** its own fixed-GUID node via the standard SetupDi `DIF_REMOVE` path (device-manager "uninstall device"), waits briefly and retries the create once. Applied to all three creation sites (fresh start ×2, resume rebuild). If healing fails the original error still surfaces through the normal enable-failure channel.
  - Note: SWD devices whose PnP status is `Error` (interface never registered) are already handled by wintun.dll itself and never reach the heal path.

---

# v3.0.2 Release Notes (2026-08-26)

## Patch: Interface-Egress VPN Route Completion & Node-Test UX

### Fixed
- **Interface-egress nodes unreachable under split-tunnel VPN (core fix)**: `IP_UNICAST_IF` binds a socket to the chosen interface, but its next-hop lookup is restricted to routes *on that interface*. A split-tunnel VPN (default-gateway off) has no route covering the proxy server's public IP, so connects failed with `WSAENETUNREACH` and the site never loaded despite the rule matching. Now a **L1-interface /32 route is auto-completed** (gateway = the interface's own IPv4, on-link semantics) whenever it is missing:
  - at **enable** time for every interface-egress node's resolved server IPs;
  - on **node CRUD hot-reload** (add/modify/delete kept symmetric);
  - and **re-completed once + retry** when an interface-egress connect fails at runtime (e.g. VPN reconnected with a changed gateway); failure surfaces as “VPN not connected or no usable route on the interface”.
  - Skipped when the interface already has a covering route (incl. full-tunnel default route); all routes are tracked by `RouteManager` and cleaned on disable.
  - IPv6 interface-egress route completion deferred to a later release (v4 only for now).

### Improved
- **Node test-button loading state**: the per-node test button now disables and shows “Testing...” while a connectivity probe runs (single click and page-open batch test both covered), restored automatically on completion.
- **Rule-test dialog layout**: the four test inputs (host / IP / port / process) in the narrow 380px dialog are now stacked vertically (label above input) instead of cramped horizontal rows; other `.form-row` usages unaffected.

---

# v3.0.1 Release Notes (2026-08-26)

## Patch: Rule-Site Unreachability & Full Functional Audit (D1-D11)

### Fixed
- **D1 Dead-gateway fallback**: removed the hardcoded `192.168.68.1` original-gateway fallback — when the gateway is unknown, /32 exclusion routes are now skipped with a warning (socket binding + L3-1 guard still protect node egress); gateway filtering no longer mis-kills 10.x LAN gateways (TUN-adapter-based check); **TUN subnet migrated 10.0.0.0/16 → 198.18.0.0/16** (RFC 2544 benchmark range) to stop swallowing 10.x LAN traffic
- **D2 Domain rules under DoH**: TLS SNI sniffing moved **before** rule matching (was only in direct/VPN branches after matching) — browsers with Secure DNS now hit domain rules on 443; sniffer first-packet is replayed on every forwarding branch; a help note in Settings explains DoH implications
- **D3 test_proxy rewrite**: node testing now uses the exact production path (domain resolution → outbound-policy connect → protocol handshake) with three-tier failure reasons (DNS / TCP / handshake); domain nodes no longer report permanently unreachable; failed results cached 15s instead of 60s
- **D4 Dangling node references**: deleting a referenced node now asks for confirmation (rules/default route are rewired to Direct); runtime logs "node missing" warnings with a request-log marker; default_route self-heals at startup

### Improved
- **D5 Node failure visibility**: channel-establish failures are counted per node (one 200ms retry, three-tier error classification) and surfaced on node cards (pulsing red dot + tooltip ≥5 failures); stats clear on successful test/disable
- **D6 Known limitation documented**: QUIC/HTTP3 UDP is dropped (DNS-only UDP) with a Settings note explaining the expected few-second TCP fallback
- **D7 Enable error handling**: route backup failure now aborts enable (prevents route leaks); all-DNS-hijack-failure aborts; IPv6 route / upstream-DNS /32 / partial DNS hijack failures become one-shot warnings shown via status toasts
- **D8 Rule test dialog parity**: optional IP / port / process inputs now feed `match_connection` (ip_cidr/port/process rules testable); miss results carry a hint when an IP is required
- **D9 save_config runtime sync**: rules/nodes changes via save_config now rebuild the rule engine and sync /32 routes + address sets (default-route changes take effect immediately)
- **D10 CDN co-location guard**: L3-1 self-loop check now also verifies the connecting process is this sidecar (user apps hitting a node's CDN edge IP are no longer hijacked); domains resolving to >4 A records skip /32 routes
- **D11 Misc**: IPv6-without-address rejection becomes a one-shot warning; `defaultRouteName` shows a friendly name ("(deleted)" instead of raw id); dead `switch_profile` RPC removed

---

# v3.0.0 Release Notes (2026-08-25)

## Major: TUN Loop Prevention & v3 Simplification

### Added
- **Node Outbound Mode (L1/L2)**: Remote nodes now bind to the physical NIC by default (direct routes added for node IPs at enable time, hot-reload on node CRUD); optional "system" mode for nodes that must traverse a system VPN
- **Runtime Loop Guards (L3)**: self-loop guard (node-address set via ArcSwap), proxy-core process guard (v2ray/clash/mihomo etc.), and high-frequency loop detection with UI banner
- **Pre-enable Conflict Scan (L4)**: external TUN adapters, external default routes, running proxy cores and DNS-hijack remnants, with a high-risk blocking dialog and coexistence guidance
- **Domain-name Nodes (O2)**: node host now accepts domains (IP fast path, DNS-cache lookup, upstream A query)
- **Process Rule Conditions (O8)**: `process_name` / `process_path` conditions exposed in the rule form
- **Settings: Loop Guard & Outbound Exclusions**: guard toggle, custom proxy-core process list, and IP/CIDR exclusion list wired to real direct routes
- **One-time v3 migration dialog** explaining removals/migrations/new features

### Removed (v3 simplification, R1-R11)
- Traffic Chains (fake implementation), fake-IP subsystem (direct-rule black hole fix), DoH/DoT config fields, hotkey RPCs, log header/body preview fields, GeoIP stub, legacy bypass textarea (migrated to outbound exclusions), Logs Stats sub-tab, TUN WIP form, dead frontend code, 9 unused Cargo dependencies and 8 unused windows features

### Changed
- **Config migration (v2.8.1 → 3.0.0)**: chain nodes filtered with dangling rule references reset to default route; `bypass_list` merged into `outbound_exclude_ips`; fake DNS cache entries purged at load
- DNS upstream resolution unified into one module (O1); TUN start/resume share adapter setup (O3); PowerShell DNS query unified (O4); rule test reuses the engine (O5); error responses unified (O6); route cleanup now accounting-driven and symmetric (O7)

<details>
<summary>中文说明</summary>

# v3.0.0 更新说明 (2026-08-25)

## 重大版本：TUN 回环防护与 v3 精简重构

### 新增
- **节点出站方式（L1/L2）**：远程节点缺省绑定物理网卡出站（启用时为节点地址添加直连路由，节点增删改热更新）；可选「跟随系统路由」以兼容系统 VPN 场景
- **运行时回环守卫（L3）**：自回环守卫、代理内核进程守卫（v2ray/clash/mihomo 等）、高频回环侦测告警（界面横幅提示）
- **启用前环境冲突扫描（L4）**：外部 TUN 适配器、外部默认路由、运行中的代理内核、DNS 劫持残留，高风险时阻断并给出共存引导
- **域名节点支持（O2）**：节点地址支持域名（IP 快路径 → DNS 缓存反查 → 上游解析）
- **进程规则条件（O8）**：规则表单开放 process_name / process_path 条件
- **设置页回环防护区**：守卫开关、自定义代理内核进程名单、出站排除列表（接入真实直连路由）
- **v3 一次性迁移说明弹窗**

### 移除（R1-R11）
- 流量链（假实现）、fake-IP 机制（修复直连规则域名黑洞）、DoH/DoT 配置字段、热键 RPC、日志头/体预览字段、GeoIP 桩、旧绕过文本域（迁移为出站排除）、日志统计子页、TUN WIP 表单、前端死代码、9 个未用 Cargo 依赖与 8 个未用 windows features

### 变更
- **配置迁移（v2.8.1 → 3.0.0）**：链式节点过滤（悬空规则重置为默认路由）；bypass_list 合并到 outbound_exclude_ips；加载时清理 fake DNS 缓存条目
- DNS 上游统一（O1）；TUN start/resume 共用适配器装配（O3）；PowerShell DNS 查询统一（O4）；规则测试复用引擎（O5）；错误响应统一（O6）；路由清理改为记账驱动对称删除（O7）

</details>

---
# v2.8.1 Release Notes (2026-08-18)

## Maintenance
- **Build File Update**: Refreshed plugin build configuration files for release pipeline alignment
- Version sync release: no functional changes

<details>
<summary>中文说明</summary>

# v2.8.1 更新说明 (2026-08-18)

## 维护
- **构建文件更新**：刷新插件构建配置文件以对齐发版流水线
- 版本同步发布：无功能性变更

</details>

---

# v2.8.0 Release Notes (2026-08-17)

## Maintenance
- Version sync release: no functional changes; aligned metadata versioning with the latest release pipeline

<details>
<summary>中文说明</summary>

# v2.8.0 更新说明 (2026-08-17)

## 维护
- 版本同步发布：无功能性变更，与最新发版流程的元数据版本对齐

</details>

---

# v2.7.0 Release Notes (2026-08-03)

## Improvements
- **Code Quality**: Extracted common utility functions into shared modules, eliminating code duplication across composables and components
- **Performance**: Optimized RulesTab matching from O(N×M) array traversal to Map-based lookup for significantly faster rule evaluation
- **Type Safety**: Eliminated all `any` types with proper TypeScript type definitions throughout the frontend
- **Logging**: Replaced `console.error` calls with unified `feLog` logging for consistent error handling
- **Architecture**: Extracted large composables into focused modules (useDns, useDriver, useProfileCrud, useProxyCore) and added reusable UI components (AppIcon, BaseModal, ColorPicker, TagInput)

## Bug Fixes
- Fixed DashboardTab using mock data and random port generation instead of real values
- Fixed SettingsTab placeholder implementations with empty function bodies
- Removed unused ProfileTab component (905 lines of dead code)

<details>
<summary>中文说明</summary>

# v2.7.0 更新说明 (2026-08-03)

## 优化改进
- **代码质量**：提取公共工具函数到共享模块，消除组合式函数和组件间的重复代码
- **性能优化**：RulesTab 规则匹配从 O(N×M) 数组遍历优化为 Map 查找，大幅提升规则求值速度
- **类型安全**：全面消除 `any` 类型，替换为完整的 TypeScript 类型定义
- **日志统一**：将 `console.error` 调用替换为统一的 `feLog` 日志处理
- **架构重构**：将大型组合式函数拆分为聚焦模块（useDns、useDriver、useProfileCrud、useProxyCore），新增可复用 UI 组件（AppIcon、BaseModal、ColorPicker、TagInput）

## Bug 修复
- 修复 DashboardTab 使用假数据和随机端口生成，改为真实值
- 修复 SettingsTab 空壳功能实现（空函数体）
- 移除无用的 ProfileTab 组件（905 行死代码）

</details>

---

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
