# v2.2.1 更新说明 (2026-09-16)

## 修复
- 修复市场安装的插件在侧边栏/气泡显示占位图标的问题——ZIP 现已包含插件图标文件
- 构建配置适配 pnpm v12（工程内部，不影响使用）

---

# v2.2.0 更新说明 (2026-09-16)

## 优化
- 随核心优化同步适配，细节打磨

---

# v2.1.0 更新说明 (2026-09-16)

## 新增
- 全新工具树界面：硬件/系统/网络/进程/外设分域浏览，实时监控 CPU·内存·磁盘·网速
- WiFi 密码、VPN 凭据、产品密钥等凭据读取能力增强

## 优化
- 代码质量加固

---

# v2.0.0 Release Notes (2026-09-09)

## Features
- **Explorer Tree UI**: Complete redesign with a 26-node grouped tree (Summary / Hardware / System / Network / Processes & Apps / Passwords & Keys / Peripherals & Ports), full-width table detail panels and a bottom realtime status bar
- **Realtime Monitoring Returns**: CPU (with live clock) / memory / disk / network gauges — off by default, 2s refresh when enabled, auto-paused while the window is hidden (sidecar warms up performance counters at startup so first use never blocks)
- **Passwords & Keys Domain** (admin-run app, fetched live with zero caching): WiFi passwords incl. WPA3, VPN credentials (built-in rasphone.pbk + DPAPI / WireGuard / OpenVPN), Windows product key (DigitalProductId decode), BitLocker recovery keys, auto-logon password, Credential Manager with best-effort blob decode (plaintext / inner-encrypted / unreadable states, no guessing)
- **New Pages**: Processes Top ranking (memory/CPU/name sort + search), Installed Apps, Startup Items, Local Users, System Health (activation / Defender / TPM / Secure Boot / power plan / page file)
- **Hardware Fixes**: memory speed falls back to ConfiguredClockSpeed (DDR5 machines no longer show "--"), GPU VRAM three-tier fallback fixes the 4 GB uint32 truncation, disks report BusType (NVMe no longer shows "IDE"), SSD detection matched by serial number, monitors decoupled from GPU resolution, machine model added
- **Graceful WiFi**: machines without a wireless adapter show a neutral empty state instead of an error banner
- **Error Transparency**: timed-out child processes are now killed instead of leaking; system health collects in four parallel lanes and surfaces the exact per-item error message in the UI (instead of a generic 30s bridge timeout)
- **VPN by Protocol**: built-in VPNs grouped by protocol (PPTP/L2TP/IKEv2/SSTP) with per-connection detail panels — auth method, data encryption requirement, gateway mode (split tunnel), remember-sign-in flag, last modified, and an honest credential-source badge (decrypted from phonebook / matched from Credential Manager / not saved on this machine, with the explanation that typing into Settings is not the same as saving)
- **Credential Manager v2**: entries grouped by credential type (Generic / Domain Password / Domain Certificate / Domain Visible Password) with filter chips and type descriptions; new columns for blob size, attribute count, target alias and comment
- **VPN Credential Fix**: rasphone.pbk passwords use the real `hex:xx,xx,...` comma format (previously unparseable, showed "no password"); NUL-wrapped DPAPI blobs trimmed; SSTP/IKEv2 credentials matched from Credential Manager `rasdial/` entries; GBK phonebooks decoded; "no password" wording corrected to "not saved or undecryptable" with storage-location hint
- **Export v2**: TXT / Markdown / JSON with optional passwords & keys section (included by default)

<details>
<summary>中文说明</summary>

# v2.0.0 更新说明 (2026-09-09)

## 功能
- **工具树界面**：整体重设计为 26 节点分组树（摘要/硬件/系统/网络/进程与应用/密码与密钥/外设与端口）+ 全宽表格详情 + 底部实时状态栏
- **实时监控回归**：CPU（含当前频率）/内存/磁盘/网速指标环，默认关闭、开启后 2s 刷新、窗口隐藏自动暂停（sidecar 启动预热性能计数器，首次使用不卡顿）
- **密码与密钥域**（程序管理员运行、实时读取零缓存）：WiFi 密码（含 WPA3）、VPN 凭据（内置 rasphone.pbk + DPAPI / WireGuard / OpenVPN）、Windows 产品密钥（注册表解码）、BitLocker 恢复密钥、自动登录密码、凭据管理器（明文/内层加密/不可读三态，不猜不骗）
- **新页面**：进程排行（内存/CPU/名称排序+搜索）、已安装应用、自启动项、本地用户、系统健康（激活/Defender/TPM/安全启动/电源计划/页面文件）
- **采集修复**：内存频率回落 ConfiguredClockSpeed（DDR5 不再显示 --）、显存三级兜底修复 4GB 截断、磁盘显示 BusType（NVMe 不再显示 IDE）、SSD 按序列号关联、显示器与 GPU 分辨率解耦、新增整机型号
- **WiFi 优雅降级**：无无线网卡机器显示中性空态而非错误横幅
- **错误透明化**：超时的子进程立即终止不再泄漏堆积；系统健康改为四泳道并行采集，单项失败在界面直接显示该项的具体错误原文（不再只看到笼统的 30s 超时提示）
- **VPN 按协议分类**：内置 VPN 按协议分组（PPTP/L2TP/IKEv2/SSTP），每连接详情面板——认证方式、数据加密要求、网关模式（分流/全局）、记住登录标志、上次修改时间、凭据来源徽章（电话簿已解密 / 凭据管理器匹配 / 本机未保存，并注明「设置界面输入 ≠ 已保存」）
- **凭据管理器 v2**：按凭据类型分组（普通/域密码/域证书/域可见密码）+ 类型过滤 chips 与说明；新增 Blob 大小、属性数、目标别名、备注字段
- **VPN 凭据修复**：电话簿密码按真实 `hex:xx,xx,...` 逗号格式解析（此前解析不了导致误显「无密码」）；DPAPI 解密结果去 NUL 包裹；SSTP/IKEv2 凭据从凭据管理器 `rasdial/` 条目自动匹配；GBK 电话簿解码；「无密码」文案修正为「未保存或不可解密」并注明存储位置
- **导出 v2**：TXT / Markdown / JSON 三格式，密码与密钥段默认包含可关闭

</details>

---

# v1.3.0 Release Notes (2026-08-18)

## Features
- **Overview Home**: New default landing page with 6 summary tiles (OS / CPU / Memory / GPU / Disk / Network), click to jump to detail pages
- **Labels Always Visible**: All card titles and field labels render immediately; unloaded values show shimmer skeletons instead of full-screen spinners
- **Inline Errors + Per-card Retry**: Load failures show an inline error banner with retry button inside each card; other cards unaffected
- **Disk Usage Progress Bars**: Partition usage rendered as 6px progress bars with threshold colors (primary / warning >75% / danger >90%)
- **Connectivity Status Badges**: Internet/gateway booleans upgraded to colored pill badges (connected / unreachable / detecting with pulse)
- **Real Refresh State**: Toolbar refresh button spin is now driven by actual RPC loading state (no more fixed 2s fake animation)
- **Pill Sidebar Highlight**: Active nav item uses a rounded pill background instead of the left bar
- Frontend-only redesign: no Rust sidecar, RPC protocol, or postMessage bridge changes

<details>
<summary>中文说明</summary>

# v1.3.0 更新说明 (2026-08-18)

## 功能
- **概览首页**：新增默认落地页，6 块摘要瓦片（操作系统/处理器/内存/显卡/磁盘/网络），点击跳转对应详情页
- **标签永在**：所有卡片标题与字段标签立即渲染，未就绪值显示流光骨架屏，取代整屏加载圈
- **错误内联化 + 单卡重试**：加载失败在卡片内显示错误横幅与重试按钮，互不影响其他卡片
- **磁盘用量进度条**：分区使用率以 6px 进度条展示，按阈值配色（主色 / >75% 警示 / >90% 错误）
- **连通性状态徽章**：互联网连接/网关可达升级为彩色胶囊徽章（已连接/不可达/检测中脉冲）
- **刷新真实状态**：顶栏刷新按钮旋转与真实 RPC 加载状态同步（移除固定 2 秒假动画）
- **侧边栏药丸高亮**：当前导航项改为圆角背景块高亮，替代左侧竖条
- 纯前端改造：Rust Sidecar、RPC 协议、postMessage 桥零变更

</details>

---

# v1.2.1 Release Notes (2026-08-18)

## Maintenance
- Version sync release: no functional changes; aligned with the latest marketplace icon loading optimization

<details>
<summary>中文说明</summary>

# v1.2.1 更新说明 (2026-08-18)

## 维护
- 版本同步发布：无功能性变更，与最新商城图标加载优化对齐

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

# v1.0.0 Release Notes (2026-08-12)

## Features
- **System Information**: Comprehensive system information collection including OS version, hostname, uptime, timezone
- **Hardware Info**: CPU details (cores, frequency), memory, disk, GPU, motherboard/BIOS
- **Network Info**: IP/MAC/gateway/DNS/DHCP configuration, WiFi connection details (SSID/signal/channel/band/rate)
- **Network Diagnostics**: Gateway reachability, Internet connectivity, public IP detection
- **Export**: One-click field/card copy, export TXT/JSON reports
- **Multi-mode**: Supports inapp, desktop (standalone window), and popup modes
- **Credential Manager**: Windows Credential Manager access for stored credentials
- **Peripheral Devices**: USB devices and connected peripherals listing

<details>
<summary>中文说明</summary>

# v1.0.0 更新说明 (2026-08-12)

## 功能
- **系统信息**：全量系统信息采集，含操作系统版本、主机名、运行时长、时区
- **硬件信息**：CPU 详情（核心数、频率）、内存、磁盘、GPU、主板/BIOS
- **网络信息**：IP/MAC/网关/DNS/DHCP 配置、WiFi 连接详情（SSID/信号/信道/频段/速率）
- **网络诊断**：网关可达性、Internet 连通性、公网 IP 检测
- **导出功能**：一键复制字段/卡片，导出 TXT/JSON 报告
- **多模式**：支持内嵌、独立窗口、弹窗三种模式
- **凭据管理器**：Windows 凭据管理器存储凭据访问
- **外设信息**：USB 设备和已连接外设列表

</details>

---

# v0.1.0 更新说明 (2026-08-11)

## 新增
- 初始版本，提供系统信息获取核心功能
