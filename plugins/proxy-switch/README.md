# Proxy Switch

> TUN-mode system-level traffic routing engine with global traffic interception, intelligent rule-based routing, and multi-proxy group management.

## Features

- **TUN Virtual NIC**: Creates a virtual network adapter via WinTun driver to intercept all application traffic (including apps that bypass system proxy)
- **Intelligent Rule Routing**: Automatically selects proxy nodes or direct connection based on domain, domain suffix, keyword, regex, IP CIDR, port, protocol, and more
- **Multi-Node Management**: Supports HTTP/SOCKS5/VPN/chain proxy with free switching between nodes
- **Proxy Chains**: Supports multi-level proxy chaining (e.g., ProxyA → VPN1 → Target Server)
- **DNS Cache**: Built-in DNS relay and cache for faster domain resolution
- **Request Log**: Real-time view of traffic rule matching and routing results
- **Driver Management**: One-click WinTun driver install, update, and uninstall
- **Rule Import**: Supports AutoProxy format rule import

## Usage

1. Open My Desktop Tools and grant administrator permission (UAC)
2. On first use, install the WinTun driver in the **Settings** page
3. Add proxy nodes in the **Nodes** page (HTTP/SOCKS5/VPN)
4. Configure routing rules in the **Rules** page (optional)
5. Toggle the switch in the **Dashboard** page to enable TUN proxy

## Notes

- This plugin requires **administrator privileges** (creating a virtual NIC requires elevation)
- WinTun driver must be installed on first use (one-click download within the plugin)
- When TUN is enabled, all system traffic will be intercepted — ensure at least one working proxy node is available
- If using V2RayN/Clash simultaneously, keep only their port listening enabled and disable their system proxy/TUN
- Data is stored locally and never uploaded

## Version History

| Version | Date | Notes |
|---------|------|-------|
| 2.5.0 | 2026-07-12 | Shortcut config, TCP logs, dashboard navigation, elevation optimization |
| 2.4.0 | 2026-06-06 | Deep fix for TUN adapter lifecycle |
| 2.3.0 | 2026-06-06 | Initial fix for TUN adapter lifecycle |
| 2.2.0 | 2026-05-25 | Proxy chains, rule tags, node testing |
| 2.1.0 | 2026-05-23 | TLS SNI extraction, IPv6 TUN support |
| 2.0.0 | 2026-06-05 | TUN mode rewrite, 100% global proxy |
| 1.2.0 | 2026-05-05 | Auto rule switching, multi-profile management |
| 1.1.0 | 2026-04-15 | System-level proxy management, proxy rule configuration |
| 1.0.0 | 2026-04-01 | Initial version (system proxy mode) |

---

**Plugin ID**: proxy-switch
**Author**: my-desktop-tools

---

<details>
<summary>中文说明</summary>

# 代理管理

> TUN 模式系统级流量路由引擎，全局流量劫持 + 规则智能路由 + 多代理组管理

## 功能介绍

- **TUN 虚拟网卡**：通过 WinTun 驱动创建虚拟网卡，拦截所有应用程序的网络流量（包括不走系统代理的程序）
- **规则智能路由**：根据域名、域名后缀、关键词、正则、IP CIDR、端口、协议等条件自动选择代理节点或直连
- **多节点管理**：支持 HTTP/SOCKS5/VPN/链式代理，多节点自由切换
- **流量链**：支持多级代理串联（如 代理A → VPN1 → 目标服务器）
- **DNS 缓存**：内置 DNS 中继与缓存，加速域名解析
- **请求日志**：实时查看流量匹配规则与路由结果
- **驱动管理**：WinTun 驱动一键安装、更新、卸载
- **规则导入**：支持 AutoProxy 格式规则导入

## 使用说明

1. 打开 My Desktop Tools，允许管理员权限请求（UAC）
2. 首次使用请在「设置」页安装 WinTun 驱动
3. 在「节点管理」页添加代理节点（HTTP/SOCKS5/VPN）
4. 在「规则管理」页配置路由规则（可选）
5. 在「仪表盘」页点击开关启用 TUN 代理

## 注意事项

- 本插件需要**管理员权限**运行（创建虚拟网卡需提权）
- 首次使用需安装 WinTun 驱动（插件内一键下载安装）
- 启用 TUN 后系统所有流量将被拦截，请确保至少有一个可用的代理节点
- 如果同时使用 V2RayN/Clash 等工具，请仅保留其端口监听功能，关闭其系统代理/TUN
- 数据存储在本地，不会上传

## 版本信息

| 版本 | 日期 | 说明 |
|------|------|------|
| 2.5.0 | 2026-07-12 | 快捷键配置、TCP日志、仪表盘导航、提权优化 |
| 2.4.0 | 2026-06-06 | TUN 适配器生命周期深度修复 |
| 2.3.0 | 2026-06-06 | TUN 适配器生命周期修复初版 |
| 2.2.0 | 2026-05-25 | 流量链管理、规则标签、节点测试 |
| 2.1.0 | 2026-05-23 | TLS SNI 提取、IPv6 TUN 支持 |
| 2.0.0 | 2026-06-05 | TUN 模式重构，100% 全局代理 |
| 1.2.0 | 2026-05-05 | 规则自动切换、多 Profile 管理 |
| 1.1.0 | 2026-04-15 | 系统级代理管理、代理规则配置 |
| 1.0.0 | 2026-04-01 | 初始版本（系统代理模式） |

---

**插件 ID**: proxy-switch
**作者**: my-desktop-tools

</details>

---

## ⚠️ Disclaimer

- **"AS IS"**: This software is provided "AS IS", without any express or implied warranty, including but not limited to merchantability, fitness for a particular purpose, and non-infringement.
- **Use at Your Own Risk**: The developer shall not be liable for any direct or indirect losses (including but not limited to data loss, system damage, business interruption) caused by the use of this software. Users must assess and bear all risks.
- **Data Backup**: It is recommended to back up important data before using this software to prevent irreversible loss.
- **Compatibility Risks**: This software may have unknown defects or be incompatible with certain system environments, hardware configurations, or third-party software. The developer does not guarantee normal operation in all environments.
- **Plugin Disclaimer**: Plugins in this application are independent modules. The developer makes no guarantee regarding the behavior, security, or stability of third-party plugins. Users must assess and bear the risks of using third-party plugins.

> Downloading or using this software indicates that you have read and agree to the above disclaimer.

<details>
<summary>中文免责声明</summary>

## ⚠️ 免责声明

- **按"原样"提供**：本软件按"原样"（AS IS）提供，开发者不提供任何明示或暗示的担保，包括但不限于适销性、特定用途适用性和非侵权担保。
- **风险自担**：用户因使用本软件而造成的任何直接或间接损失（包括但不限于数据丢失、系统损坏、业务中断等），开发者不承担任何责任。请用户自行评估并承担使用风险。
- **数据备份**：建议在使用本软件前备份重要数据，以防意外情况导致不可恢复的丢失。
- **兼容性风险**：本软件可能存在未知缺陷，或与特定的系统环境、硬件配置、第三方软件不兼容，开发者不保证在所有环境下均可正常运行。
- **插件免责**：本应用的插件由独立模块构成，开发者不对第三方插件的行为、安全性及稳定性作出任何保证。用户应自行评估并承担使用第三方插件的风险。

> 下载或使用本软件即表示您已阅读并同意以上免责声明。

</details>
