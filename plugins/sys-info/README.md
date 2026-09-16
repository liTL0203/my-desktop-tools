# 系统信息

> 系统信息一站式工具箱：工具树式浏览全部软硬件信息，实时监控系统负载，随时查看 WiFi 密码、产品密钥等关键凭据

## 功能介绍

- **工具树导航**：左侧 26 节点分类树（摘要 / 硬件 / 系统 / 网络 / 进程与应用 / 密码与密钥 / 外设与端口），信息密度高、点哪看哪
- **实时监控**：CPU（含当前频率）/ 内存 / 磁盘 / 网速四指标环，默认关闭、开启后 2 秒刷新，窗口隐藏自动暂停；底部状态栏常驻最新值
- **密码与密钥**（本机自用，管理员运行时可用）：
  - WiFi 密码明文（含 WPA3 网络）
  - VPN 凭据：Windows 内置 VPN 账号/PSK、WireGuard 隧道私钥、OpenVPN 配置
  - Windows 产品密钥（注册表解码）与固件 OEM 密钥
  - BitLocker 恢复密钥（48 位）
  - 开机自动登录密码
  - 凭据管理器清单（应用明文存储的直接显示，加密存储的如实标注）
- **硬件全量**：CPU 规格、内存插槽布局与频率、磁盘 BusType/分区/SMART 健康、GPU 显存精确值与分辨率、电池健康度、主板/BIOS、显示器
- **系统健康**：Windows 激活、Defender 状态、TPM、安全启动、电源计划、页面文件
- **进程与应用**：进程 Top 排行（内存/CPU/名称排序 + 搜索）、已安装应用清单、开机自启动项
- **网络诊断**：Internet—公网 IP—网关—本机四节点链路图 + 探测明细
- **报告导出**：TXT / Markdown / JSON 三格式，可选包含密码与密钥

## 使用说明

1. 打开 My Desktop Tools，进入「系统信息」
2. 左侧树点击分类查看对应信息（顶部搜索框可过滤当前页表格）
3. 摘要页点「实时监控」开关开启实时指标（仅会话内有效，关闭即停）
4. 「密码与密钥」组点击眼睛图标显示明文，「全部复制」一次带走
5. 顶部「导出」选择格式与是否包含密码，生成报告文件

## 注意事项

- 本插件仅做只读信息展示，不会修改任何系统设置、不结束进程、不写注册表
- 信息通过 WMI 与系统命令获取；TPM / 安全启动 / SMART / BitLocker / WPA3 密码需要管理员权限——My Desktop Tools 以管理员启动时自动全部可用
- 凭据管理器中部分条目由应用自行加密（如 git），会如实标注「内层加密」而不是显示乱码
- 密码与密钥每次进入页面实时读取，不做缓存；导出报告默认包含密码，可按需关闭
- 公网 IP 查询使用外部 API（ipify.org），网络受限时可能获取失败
- 电池节点与 WiFi 密码节点在无电池 / 无无线网卡的机器上自动隐藏

## 版本信息

| 版本 | 日期 | 说明 |
|------|------|------|
| 2.0.0 | 2026-09-09 | 工具树界面重设计；实时监控回归；密码与密钥域（WiFi/VPN/产品密钥/BitLocker/自动登录）；进程与应用页；采集修复（内存频率/显存截断/NVMe 接口/SSD 关联/WiFi 无卡降级/显示器归属） |
| 1.3.0 | 2026-08-18 | 概览瓦片首页 + 骨架屏 + 单卡重试 |
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
