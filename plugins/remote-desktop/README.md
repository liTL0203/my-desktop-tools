# 内网远程桌面

> 只在内网工作的远程控制：自动发现设备、一键连接、双向剪贴板、无人值守被控。无账号、无中继服务器，流量全程不出内网。

## 功能介绍

- **设备发现**：自动扫描同一网段内安装了本插件的电脑；不同网段但网络互通时，可直接输入对方 IP 连接
- **远程控制**：通过 RustDesk 引擎（开源软件）打开远程画面，鼠标键盘直接操作
- **双向剪贴板**：本机和远程电脑之间直接 Ctrl+C / Ctrl+V，文字即拷即粘
- **文件传输**：连接后在 RustDesk 窗口内使用双栏文件传输
- **无人值守**：被控电脑装一次系统服务、设一个固定密码，之后开机即可被连接，无需有人值守
- **多台同时连**：可同时远程多台电脑，会话页统一管理、一键断开
- **RDP 连接**（可选）：对方是 Windows 专业版时可改用系统自带 RDP 通道（注意：会锁定对方桌面）
- **内网专用**：只允许连接内网地址，公网无法接入——这是刻意设计，保护你的电脑

## 使用说明

### 我要控制别人（主控端）

1. 打开插件，进入「设备」页，点击**重新扫描**，等待列出同网段的在线设备
2. 扫不到时（跨网段、AP 隔离），在右上角输入对方 **IP 或 IP:端口** 直接连接
3. 点**远程连接**，输入对方设置的访问密码（或选择"请求对方确认"）
4. 连接成功后，RustDesk 窗口会自动打开远程画面，直接操作即可
5. 「会话」页可查看所有进行中的连接，并可一键断开

### 我要被别人控制（被控端）

1. 打开插件，进入「被控端」页
2. 点击**安装为系统服务**（需要管理员授权一次），装完重启电脑后开机自启
3. 设置一个**固定访问密码**并选择"固定密码（推荐）"模式
4. 保持**允许被内网发现**开启；若不希望被扫描到，可关闭（隐身），对方仍可通过 IP 直连你
5. 之后无需任何操作，主控方凭密码即可连接

### 首次使用前

远程画面由 RustDesk 引擎承载，首次使用请在「设置 → 引擎管理」中三选一：

- **从官方源下载**（推荐）：自动下载便携版并校验完整性
- **本地导入**：已自行下载好 RustDesk zip 或 exe 时，填入路径导入
- **指定已有安装**：本机已安装 RustDesk 时，直接填入其 rustdesk.exe 路径

## 注意事项

- 本插件**不做公网远程**：两台电脑必须在同一个内网中（或内网内部路由互通），且不能隔着公网
- 自动发现只覆盖**同一网段**；不同网段但互通的内网，请直接输入对方 IP 连接
- 引擎按需下载（约 40-70MB），不会随插件打包；插件只分发 RustDesk 官方原版（AGPL-3.0 开源软件），不修改其源码
- 本插件不保存任何访问密码：主控侧每次连接时输入；被控侧密码由 RustDesk 引擎保管
- 安装被控服务后，建议重新设置一次访问密码（引擎在服务模式下的配置独立于普通模式）
- 断开 RustDesk 会话时，若引擎工作在单实例模式，会关闭其全部控制窗口（无法精确断开单一路）
- 实时查看"谁在连我"暂不支持（引擎未提供查询接口），可关注服务运行状态
- 所有数据（历史记录、设置、设备列表）保存在本机，不会上传任何服务器

## 版本信息

| 版本 | 日期 | 说明 |
|------|------|------|
| 0.1.0 | 2026-09-14 | 初始版本：内网发现/手动 IP 直连、RustDesk 引擎连接、双向剪贴板（引擎承载）、无人值守服务管理、画质预设、RDP 直通、多会话管理 |

---

**插件 ID**: remote-desktop
**作者**: li_TL

---

<details>
<summary>English</summary>

# LAN Remote Desktop

> Remote control that only works on the intranet: automatic device discovery, one-click connection, two-way clipboard, unattended access. No account, no relay server — traffic never leaves the LAN.

## Features

- **Device discovery**: automatically scans computers on the same subnet that have this plugin installed; across different but interconnected subnets, connect directly by entering the peer's IP
- **Remote control**: opens the remote screen through the RustDesk engine (open-source software); operate it directly with mouse and keyboard
- **Two-way clipboard**: Ctrl+C / Ctrl+V straight between the local and remote computer — copy on one side, paste on the other
- **File transfer**: after connecting, use the dual-pane file transfer inside the RustDesk window
- **Unattended access**: install the system service once on the controlled computer and set a fixed password; from then on it can be connected whenever it boots, with no one at the desk
- **Multiple simultaneous sessions**: remote into several computers at once; manage them all on the Sessions page and disconnect with one click
- **RDP connection** (optional): when the other side runs Windows Pro, switch to the system's built-in RDP channel (note: this locks the peer's desktop)
- **LAN-only**: only intranet addresses can be connected; access from the public internet is impossible — a deliberate design that protects your computer

## Usage

### Controlling Others (Controller Side)

1. Open the plugin, go to the "Devices" page, click **Rescan**, and wait for online devices on the same subnet to be listed
2. If nothing is found (cross-subnet, AP isolation), enter the peer's **IP or IP:port** in the top-right corner to connect directly
3. Click **Remote Connect** and enter the access password set on the peer (or choose "Request peer confirmation")
4. Once connected, a RustDesk window opens the remote screen automatically — just start operating
5. The "Sessions" page shows every connection in progress and supports one-click disconnect

### Being Controlled (Controlled Side)

1. Open the plugin and go to the "Controlled" page
2. Click **Install as System Service** (requires administrator approval once); after installation and a reboot, it starts automatically at boot
3. Set a **fixed access password** and choose the "Fixed password (recommended)" mode
4. Keep **Allow LAN Discovery** enabled; if you don't want to be discoverable, turn it off (stealth mode) — others can still connect to you directly by IP
5. After that, no further action is needed: the controller can connect with the password

### Before First Use

The remote screen is powered by the RustDesk engine. On first use, choose one of the three options under "Settings → Engine Management":

- **Download from the official source** (recommended): automatically downloads the portable build and verifies its integrity
- **Local import**: if you have already downloaded a RustDesk zip or exe yourself, enter its path to import
- **Point to an existing install**: if RustDesk is already installed on this machine, just enter the path to its rustdesk.exe

## Notes

- This plugin **does not do public-internet remote control**: both computers must be in the same intranet (or routable inside it) and must not be separated by the public internet
- Automatic discovery only covers the **same subnet**; for different but interconnected subnets, connect by entering the peer's IP directly
- The engine is downloaded on demand (about 40-70MB) and is not bundled with the plugin; the plugin only distributes the official unmodified RustDesk build (AGPL-3.0 open-source software) and does not modify its source code
- The plugin never stores any access password: the controller side types it in on every connection; the controlled side's password is kept by the RustDesk engine
- After installing the controlled-side service, set the access password again (the engine's service-mode configuration is independent of normal mode)
- When disconnecting a RustDesk session, if the engine runs in single-instance mode, all of its control windows are closed (a single connection cannot be disconnected precisely)
- Viewing "who is connected to me" in real time is not yet supported (the engine provides no query interface); watch the service status instead
- All data (history, settings, device list) is stored locally and is never uploaded to any server

## Version History

| Version | Date | Notes |
|---------|------|-------|
| 0.1.0 | 2026-09-14 | Initial release: LAN discovery / manual IP direct connection, RustDesk engine connection, two-way clipboard (engine-powered), unattended service management, quality presets, RDP passthrough, multi-session management |

**Plugin ID**: remote-desktop
**Author**: li_TL

</details>

---

## ⚠️ Disclaimer

- **"AS IS"**: This software is provided "AS IS", without any express or implied warranty, including but not limited to merchantability, fitness for a particular purpose, and non-infringement.
- **Use at Your Own Risk**: The developer shall not be liable for any direct or indirect losses (including but not limited to data loss, system damage, business interruption) caused by the use of this software. Users must assess and bear all risks.
- **Data Backup**: It is recommended to back up important data before using this software to prevent irreversible loss.
- **Compatibility Risks**: This software may have unknown defects or be incompatible with certain system environments, hardware configurations, or third-party software. The developer does not guarantee normal operation in all environments.
- **Plugin Disclaimer**: Plugins in this application are independent modules. The developer makes no guarantee regarding the behavior, security, or stability of third-party plugins. Users must assess and bear the risks of using third-party plugins.

> Downloading or using this software indicates that you have read and agree to the above disclaimer.
