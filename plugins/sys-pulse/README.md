# 性能速览

> sys-pulse - 实时系统监控：悬浮 HUD、进程归因、流量账本、智能告警。免管理员、无驱动

## 功能介绍

- **悬浮 HUD**：屏幕角落常驻监控条，三形态可切换（胶囊条 / 纯文字 / 迷你图卡片），显示项（网速/CPU/内存/GPU/磁盘/电池）自定义；按住左键拖到任意位置（松手记忆），双击展开「此刻是谁在吃资源」归因弹层
- **真右键菜单**：右键悬浮条弹出完整菜单——显示项目、形态、网速单位、按负载着色、锁定位置、全屏隐藏、关闭，即改即生效
- **贴桌面不打扰**：字号三档与背景三态（深色玻璃/浅色玻璃/纯文字）适配不同壁纸；全屏看视频或打游戏时自动隐藏让位，退出全屏自动恢复
- **实时监控**：CPU（总/每核）、内存、GPU 利用率与显存、磁盘读写、电池状态、各网卡上下行速率，数据每秒推送（非轮询）
- **进程归因**：Top 进程排行（CPU/内存/网络连接徽标），全量进程表支持排序；"卡的时候是谁干的"一键回答
- **流量账本**：按网卡逐日记账（跨重启不跳变），月度套餐额度与 80% / 95% 超额提醒，近 14 天趋势图，活跃连接进程列表
- **智能告警**：CPU 持续过载、内存吃紧、网络断连、电池低电、磁盘不足五条内置规则——阈值需**持续达标**才触发（防抖，不闪不轰炸），每条告警自动保存当时的进程快照，可随时回放
- **主题与皮肤**：跟随核心明暗主题，五种强调色一键切换

## 使用说明

1. 打开 My Desktop Tools，进入左侧导航「性能速览」
2. 悬浮条默认开启；右键悬浮条即可调整显示项/形态/单位等着色项，更多选项在「设置」页
3. 双击悬浮条 → 展开归因弹层（Top 进程速览）；按 Esc 或点 × 关闭；单击悬浮条不会误触任何操作
4. 拖动悬浮条到顺手的位置即自动记忆；「锁定位置」可防误碰拖动
5. 「流量账本」页启用套餐提醒并填写额度（GB）与重置日，即可在用量达 80% / 95% 时收到气泡与提示音
6. 「告警」页可调整每条规则的阈值/持续时长/通知方式，点击历史记录的「回放当时」查看触发时刻的进程快照

## 注意事项

- **全程免管理员、无内核驱动**：GPU 走系统性能计数器，显存走显卡驱动接口，均无需提权
- **温度监控不在范围内**：读取温度需要内核驱动（有杀毒软件误报与稳定性风险），本插件刻意不提供
- 部分老显卡/虚拟机（如 VMware）可能无 GPU 利用率计数器，此时 GPU 显示 `--` 属正常降级
- 流量账本为网卡总量精确记账；"活跃连接进程"为连接数归因（哪个应用在联网），非字节级分应用统计
- 数据（设置/账本/告警历史）仅存储在本地 `%APPDATA%\my-desktop-tools\plugin-data\sys-pulse\`，不会上传
- 插件随应用启动自动运行（悬浮条与告警需要后台采集）；在插件管理页可停止

## 版本信息

| 版本 | 日期 | 说明 |
|------|------|------|
| v0.1.0 | 2026-10-01 | 初始版本 |

---

<details>
<summary>English</summary>

# Sys Pulse

> sys-pulse - Real-time system monitor: floating HUD, process attribution, traffic ledger, smart alerts. No admin rights, no drivers

## Features

- **Floating HUD**: an always-on-top quick strip in the corner, three form factors (glass pill / minimal text / mini chart card), configurable items (network / CPU / RAM / GPU / disk / battery) and anchoring; click to open the "who is eating my resources" attribution panel
- **Real-time metrics**: CPU (total & per-core), memory, GPU utilization & VRAM, disk I/O, battery, per-adapter up/down speeds — pushed every second (no polling)
- **Process attribution**: top processes ranked by CPU / memory with TCP/UDP connection badges; full process table with sorting
- **Traffic ledger**: per-adapter daily accounting (reboot-safe), monthly quota with 80% / 95% alerts, 14-day trend chart, active-connection processes
- **Smart alerts**: five built-in rules (CPU overload, memory pressure, network down, low battery, low disk) with sustained-duration debouncing; every alert stores a process snapshot for later replay
- **Theme & skins**: follows the host light/dark theme, five accent colors

## Usage

1. Open My Desktop Tools and navigate to "Sys Pulse" in the sidebar
2. The HUD is enabled by default; switch form factor, items, anchor and sampling interval on the Settings page
3. Click the HUD to open the attribution panel; close it with Esc or the × button
4. On the Traffic Ledger page, enable quota alerts and fill in the limit (GB) and reset day
5. On the Alerts page, tune thresholds / durations / notification styles, and click "Replay" on any history entry to inspect the process snapshot at that moment

## Notes

- Runs entirely without admin rights and without kernel drivers
- Temperature monitoring is intentionally out of scope (kernel drivers risk antivirus false positives and instability)
- Some older GPUs / virtual machines (e.g. VMware) lack GPU engine counters; the GPU tile then shows `--` as a graceful fallback
- The ledger tracks exact per-adapter totals; per-app attribution is connection-count based, not byte-exact
- All data (settings / ledger / alert history) stays local in `%APPDATA%\my-desktop-tools\plugin-data\sys-pulse\`
- The plugin auto-starts with the app (the HUD and alerts need background sampling); you can stop it on the plugin management page

| Version | Date | Notes |
|---------|------|-------|
| v0.1.0 | 2026-10-01 | Initial release |

</details>

---

## ⚠️ Disclaimer

- **"AS IS"**: This software is provided "AS IS", without any express or implied warranty, including but not limited to merchantability, fitness for a particular purpose, and non-infringement.
- **Use at Your Own Risk**: The developer shall not be liable for any direct or indirect losses (including but not limited to data loss, system damage, business interruption) caused by the use of this software. Users must assess and bear all risks.
- **Data Backup**: It is recommended to back up important data before using this software to prevent irreversible loss.
- **Compatibility Risks**: This software may have unknown defects or be incompatible with certain system environments, hardware configurations, or third-party software. The developer does not guarantee normal operation in all environments.
- **Plugin Disclaimer**: Plugins in this application are independent modules. The developer makes no guarantee regarding the behavior, security, or stability of third-party plugins. Users must assess and bear the risks of using third-party plugins.

> Downloading or using this software indicates that you have read and agree to the above disclaimer.
