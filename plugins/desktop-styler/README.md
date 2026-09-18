# 桌面美化

AI 驱动的 Windows 桌面美化工具：把桌面变成 mac 风格的 Dock + 顶栏 + 时钟小组件，配合壁纸与系统外观一键切换；所有修改自动快照，随时一键还原。

## 功能

- **Dock 启动栏**：mac 风应用启动栏，支持左/下/右停靠、图标大小、悬停波浪放大、毛玻璃底色调节
- **顶部菜单栏**：屏幕顶部状态条（时间/电量，默认关闭）
- **时钟小组件**：桌面常驻时钟（左侧/右侧）
- **系统设置（白名单）**：壁纸切换（内置渐变预设）、系统深浅色、任务栏自动隐藏；任务栏对齐需 Windows 11
- **美化方案**：内置「mac 深色 / 极简工作 / 系统默认」三方案，可保存当前配置为自定义方案
- **AI 调参**：对 mydt 的 AI 助手说一句话（如「帮我把桌面弄成 mac 深色风」），AI 列出参数变更、经你确认后应用；支持增量微调（「dock 图标再大一点」）
- **安全还原**：每次系统修改前自动快照原始值；一键还原系统默认；插件界面异常时对 AI 说「还原默认」同样生效

## 使用方法

1. 在快捷启动或插件列表打开「桌面美化」
2. 手动调参：左侧选分区，中间调参数，右侧实时预览即时生效
3. AI 调参：打开 AI 助手直接描述想要的效果，确认变更卡片即可
4. 还原：「方案与还原」页一键还原，或对 AI 说「全部还原系统默认」

## 注意事项

- 系统设置修改影响 Windows 全局；插件会在修改前自动快照，可精确还原
- 任务栏对齐项需要 Windows 11（Windows 10 上显示禁用）
- 主题包（mydt 自身窗口换肤）将在 v0.2.0 提供
- 修改系统深浅色会联动影响所有应用的明暗外观

## 版本信息

| 版本 | 日期 | 说明 |
|------|------|------|
| 0.1.0 | 2026-09-17 | 首版：Dock/顶栏/时钟三桌面元素 + 系统设置四项 + 方案/快照/一键还原 + AI 技能组 7 项 |

---

<details>
<summary>English</summary>

AI-driven Windows desktop beautifier: mac-style Dock, top bar and clock widgets with one-switch wallpapers and system appearance; every change is snapshotted and restorable in one click.

## Features

- **Dock**: mac-style launcher with left/bottom/right anchoring, icon size, wave hover magnification and glass tint controls
- **Top menu bar**: status strip with clock/battery (off by default)
- **Clock widget**: persistent desktop clock (left/right)
- **System settings (whitelisted)**: wallpaper presets, system light/dark, taskbar auto-hide; taskbar alignment requires Windows 11
- **Profiles**: built-in "mac dark / minimal work / system default" plus custom saved profiles
- **AI tuning**: tell mydt's AI assistant what you want ("make my desktop mac dark style"), confirm the change card and it applies; incremental tweaks supported
- **Safe restore**: every system change is snapshotted first; one-click restore to system defaults; telling AI "restore defaults" works even if the plugin UI is broken

## Usage

1. Open "Desktop Styler" from Quick Launcher or the plugin list
2. Manual tuning: pick a section on the left, adjust in the middle, watch the live preview
3. AI tuning: describe the effect to the AI assistant and confirm
4. Restore: one-click on "Profiles & Restore", or tell the AI

## Notes

- System changes affect Windows globally; they are snapshotted before applying and precisely restorable
- Taskbar alignment requires Windows 11 (disabled on Windows 10)
- Theme pack (mydt's own windows) arrives in v0.2.0
- System light/dark affects all apps

## Version

| Version | Date | Notes |
|---------|------|-------|
| 0.1.0 | 2026-09-17 | Initial: Dock/topbar/clock elements + 4 system settings + profiles/snapshots/one-click restore + 7 AI skills |

</details>

---

## ⚠️ Disclaimer

- **"AS IS"**: This software is provided "AS IS", without any express or implied warranty, including but not limited to merchantability, fitness for a particular purpose, and non-infringement.
- **Use at Your Own Risk**: The developer shall not be liable for any direct or indirect losses (including but not limited to data loss, system damage, business interruption) caused by the use of this software. Users must assess and bear all risks.
- **Data Backup**: It is recommended to back up important data before using this software to prevent irreversible loss.
- **Compatibility Risks**: This software may have unknown defects or be incompatible with certain system environments, hardware configurations, or third-party software. The developer does not guarantee normal operation in all environments.
- **Plugin Disclaimer**: Plugins in this application are independent modules. The developer makes no guarantee regarding the behavior, security, or stability of third-party plugins. Users must assess and bear the risks of using third-party plugins.

> Downloading or using this software indicates that you have read and agree to the above disclaimer.
