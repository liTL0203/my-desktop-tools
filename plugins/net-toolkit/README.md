# 网络工具箱

一体化网络运维工具箱。与在线工具网站最大的不同：所有探测都从你这台电脑直接发起——真实 ICMP Ping、TCP 端口连通、自定义 DNS 服务器、远程唤醒——测出来的就是你自己遇到的网络状况。

## 功能

**总览**：本机网络状态一目了然——互联网连通、公网 IP（含归属地）、内网 IP、默认网关、DNS、活动网卡；最近的探测历史一键重跑。

**Ping 探测**：本机真实 ICMP（无需管理员）。最多 6 个目标并排对比：丢包率、最小/平均/最大延迟、抖动、趋势缩略图；点击任一目标查看实时延迟曲线（含阈值线、超阈值黄点、丢包红叉）与回包日志。支持持续监控与固定 20 次两种模式，结果可导出 CSV。

**路由追踪**：真实 ICMP 逐跳探测（免管理员），每跳 3 次探测，展示延迟条形、跳点 IP、反向解析域名与丢包情况；到达目标 / 不可达自动判别，可中途停止。

**端口扫描**：TCP 直连探测，开放 / 关闭 / 过滤三态与握手延迟。内置常用 20 端口、Web、数据库、远程访问、邮件五套预设，也支持 `80,443,8000-8100` 自定义写法。并发与超时可调，高危端口（SMB / RDP / VNC / Redis 等）附风险提示。

**DNS 查询**：一个域名同时发往最多 8 台 DNS 服务器（阿里 / 腾讯 / 114 / 谷歌 / Cloudflare / 路由器 / 自定义），并排对比解析结果、TTL 与解析耗时；结果不一致的会被标出——DNS 刚切换时一眼看出谁还在返回旧记录。支持 A / AAAA / CNAME / MX / TXT / NS / SOA / PTR / CAA 全部记录类型。

**Whois**：查询域名或 IP 的注册信息——自动从 IANA 根服务器跟随到注册局 / 注册商（最多两跳），注册商、注册组织、创建 / 到期时间、状态、名称服务器等关键字段以中文标签摘要展示，并可查看原始记录。

**IP 计算**（完全离线）：子网计算器（网络地址 / 广播 / 掩码 / 反掩码 / 可用范围 / 二进制，一键复制）；IPv4 点分、整数、二进制、十六进制互转；IPv6 展开 / 压缩；VLSM 子网规划器——按各部门主机数自动划分，结果可直接抄进路由器。

**局域网**：Wake-on-LAN 远程唤醒（保存设备列表，魔术包连发 3 次）；MAC 厂商识别（内置 OUI 离线数据库）与随机本地 MAC 生成；ARP 邻居表（自动标注每台设备的厂商，可发现陌生设备）。

**HTTP·证书**：一次请求拆成 DNS / TCP / TLS / 等待首字节 / 下载五段计时，慢在哪一步一目了然；重定向链完整可视化；响应头清单；SSL 证书的颁发者、有效期、剩余天数徽章与备用域名（SAN）。

**全局**：任意界面选中 IP、域名或 URL，右键快捷操作即可直达对应探测；每个功能都有「?」悬停说明；明暗双主题。

## 使用方法

1. 首页 → 网络管控分类 → 打开「网络工具箱」；也可在插件管理中设为独立窗口
2. 总览页确认本机网络状态，点击工具卡片进入对应功能
3. 探测类功能填目标后点开始即可；Ping / 端口扫描支持中途停止
4. 局域网唤醒前，需在目标电脑 BIOS / 固件中开启 Wake-on-LAN
5. 选中任意 IP / 域名 / URL 文本 → 中键快捷面板 →「网络探测」自动识别并带入对应页签

## 注意事项

- 端口扫描请仅用于自己的设备或已获授权的目标
- 公网 IP 与归属地查询需要联网，其余功能全部本地完成、离线可用
- 持续监控模式在窗口关闭后停止（后台常驻监控规划于后续版本）
- Ping 使用系统 ICMP 接口，无需管理员权限；部分企业 VPN 环境可能拦截探测

## 版本信息

| 版本 | 日期 | 说明 |
|------|------|------|
| 0.1.0 | 2026-09-28 | 首个开发版本 |

---

<details>
<summary>English</summary>

# Net Toolkit

An all-in-one network toolkit. The biggest difference from online tools: every probe runs from your own machine — real ICMP ping, TCP port connects, custom DNS servers, Wake-on-LAN — so the results reflect the network you actually experience.

## Features

**Overview**: local network at a glance — connectivity, public IP (with geo), LAN IP, gateway, DNS, active adapter; recent probes with one-click rerun.

**Ping**: real ICMP from this PC (no admin required). Up to 6 targets side by side: loss, min/avg/max latency, jitter and trend sparklines; click any target for the live latency chart (threshold line, warning dots, loss marks) and reply log. Continuous monitoring or fixed 20-ping mode; export to CSV.

**Port Scan**: TCP connect with open/closed/filtered states and handshake latency. Presets (common 20 / web / database / remote / mail) plus custom ranges like `80,443,8000-8100`. Adjustable concurrency and timeout; high-risk ports (SMB / RDP / VNC / Redis) flagged.

**DNS**: query one domain at up to 8 servers simultaneously (Ali / Tencent / 114 / Google / Cloudflare / router / custom) and compare answers, TTL and timing side by side; mismatches are highlighted — right after a DNS switch you instantly see who still serves the old record. All record types: A / AAAA / CNAME / MX / TXT / NS / SOA / PTR / CAA.

**IP Calc** (fully offline): subnet calculator (network / broadcast / mask / wildcard / usable range / binary, copy with one click); IPv4 dotted / integer / binary / hex conversions; IPv6 expand / compress; VLSM planner — allocate subnets by each department's host count, ready to paste into your router.

**LAN**: Wake-on-LAN with a saved device list (3 magic packets per wake); MAC vendor lookup (offline OUI database) and random local MAC generation; ARP neighbor table with automatic vendor labels.

**HTTP / Cert**: every request split into DNS / TCP / TLS / first-byte / download timing; full redirect chain; response headers; TLS certificate issuer, validity, days-left badge and SANs.

**Global**: select any IP, domain or URL anywhere and the quick-action menu jumps straight to the right probe; every feature has a '?' hover explanation; dark and light themes.

## Usage

1. Home → Network category → open "Net Toolkit"; it can also run as a standalone window
2. Check the overview page, then click a tool card to enter a feature
3. Fill in a target and press start; ping and port scan can be stopped midway
4. Enable Wake-on-LAN in the target machine's BIOS/firmware before waking it
5. Select any IP / domain / URL text → middle-click quick panel → "Net Probe" routes it to the right tab

## Notes

- Only scan devices you own or are authorized to test
- Public IP lookup needs internet; everything else works fully offline
- Continuous monitoring stops when the window closes (background monitoring is planned)
- Ping uses the system ICMP API and needs no admin rights; some corporate VPNs may block probes

## Version History

| Version | Date | Notes |
|---------|------|-------|
| 0.1.0 | 2026-09-28 | Initial development release |

</details>

---

## ⚠️ Disclaimer

- **"AS IS"**: This software is provided "AS IS", without any express or implied warranty, including but not limited to merchantability, fitness for a particular purpose, and non-infringement.
- **Use at Your Own Risk**: The developer shall not be liable for any direct or indirect losses (including but not limited to data loss, system damage, business interruption) caused by the use of this software. Users must assess and bear all risks.
- **Data Backup**: It is recommended to back up important data before using this software to prevent irreversible loss.
- **Compatibility Risks**: This software may have unknown defects or be incompatible with certain system environments, hardware configurations, or third-party software. The developer does not guarantee normal operation in all environments.
- **Plugin Disclaimer**: Plugins in this application are independent modules. The developer makes no guarantee regarding the behavior, security, or stability of third-party plugins. Users must assess and bear the risks of using third-party plugins.

> Downloading or using this software indicates that you have read and agree to the above disclaimer.
