# 系统信息

> 系统信息插件 - 一键获取电脑系统、硬件、网络全量信息，支持实时监控与报告导出

## 功能介绍

- **硬件信息**：CPU 型号/核心数/主频/缓存、内存容量/频率/插槽/型号、磁盘型号/SSD 标识/分区使用率、GPU 型号/显存/分辨率、主板/BIOS 版本
- **系统信息**：操作系统版本/Build 号/架构、计算机名、运行时长、时区、安装日期
- **网络信息**：本机 IP/MAC/子网掩码/网关/DNS/DHCP 配置
- **WiFi 信息**：当前连接的 SSID/信号强度/频段/信道/速率
- **实时监控**：CPU/内存/磁盘使用率环形图（30 秒自动刷新），进程 Top 10
- **连通性检测**：网关可达性、Internet 连通性、公网出口 IP
- **报告导出**：一键复制字段或卡片，导出 TXT/JSON 格式报告

## 使用说明

1. 打开 My Desktop Tools
2. 进入左侧导航栏的「系统信息」页面
3. 左侧选择信息分类（概览/系统/硬件/网络/进程），右侧查看详情
4. 点击卡片右上角「复制」按钮复制信息
5. 点击顶部「导出」按钮导出完整报告

## 注意事项

- 本插件仅做只读信息展示，不会修改任何系统设置
- 大部分信息通过 WMI 和系统命令获取，无需管理员权限
- WiFi 信息通过 `netsh` 命令获取，兼容中英文 Windows 系统
- 实时监控数据每 30 秒自动刷新，可手动点击刷新按钮立即更新
- 公网 IP 查询使用外部 API（ipify.org），网络受限时可能获取失败

## 版本信息

| 版本 | 日期 | 说明 |
|------|------|------|
| 0.1.0 | 2026-08-11 | 初始版本 |

---

**插件 ID**: sys-info
**作者**: My Desktop Tools

---

## ⚠️ Disclaimer

- **"AS IS"**: This software is provided "AS IS", without any express or implied warranty, including but not limited to merchantability, fitness for a particular purpose, and non-infringement.
- **Use at Your Own Risk**: The developer shall not be liable for any direct or indirect losses (including but not limited to data loss, system damage, business interruption) caused by the use of this software. Users must assess and bear all risks.
- **Data Backup**: It is recommended to back up important data before using this software to prevent irreversible loss.
- **Compatibility Risks**: This software may have unknown defects or be incompatible with certain system environments, hardware configurations, or third-party software. The developer does not guarantee normal operation in all environments.
- **Plugin Disclaimer**: Plugins in this application are independent modules. The developer makes no guarantee regarding the behavior, security, or stability of third-party plugins. Users must assess and bear the risks of using third-party plugins.

> Downloading or using this software indicates that you have read and agree to the above disclaimer.
