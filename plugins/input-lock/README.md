# 防误触锁定

> 清理键盘鼠标时的输入防护罩：一键锁定全局键鼠输入，擦拭误触全部拦下，屏幕保持常显。

## 功能介绍

- **一键防护**：点击「开始防护」即锁定全局键盘与鼠标输入，擦拭产生的乱按乱点不会传给任何程序，屏幕保持可见不熄灭
- **快速开启**：全局热键 `Ctrl+Alt+K` 随时唤起控制窗（也可在快捷启动中搜「防触 / 锁定」），一键进入防护
- **专属手势解锁**：默认 2 秒内连按 `Esc ×3` 解锁——刻意设计，擦拭的零散乱按不会误触发；可在设置中切换为「长按 Esc 3 秒」或「Ctrl+Alt+F」
- **多重自动恢复兜底**：最长锁定时长到点强制自动解除（默认 30 分钟，5-120 可调、不可关闭）；即使本插件异常退出，系统也会立即恢复输入
- **锁定状态一目了然**：屏幕顶部常驻横幅显示剩余时间与已拦截次数，并提示当前解锁方式
- **灵活范围**：全部 / 仅键盘 / 仅鼠标三种锁定范围，适配不同清理场景
- **开窗即锁**（可选）：开启后热键唤起控制窗即自动 3 秒倒计时进入防护，倒计时内可取消

## 使用方法

1. 清理键盘鼠标前，按 `Ctrl+Alt+K`（或在主窗口打开「防误触锁定」）
2. 选择时长（手动 / 5 / 15 / 30 分钟）后点击「开始防护」
3. 放心擦拭；顶部横幅实时显示剩余时间与拦截次数
4. 清理完成后按当前解锁手势（默认连按 `Esc ×3`）恢复输入

## 注意事项

- `Ctrl`+`Alt`+`Del` 是操作系统级安全序列，任何软件都不能拦截——若遇任何异常，按它即可重新掌控电脑
- 防护期间若有系统弹窗（如 UAC 提权确认）出现，需解除防护后再处理
- 触控屏与触控板的点击绝大多数会被拦截；个别驱动级独占模式的外设（部分数位板、手柄）不在拦截范围
- 电源键 / 休眠按钮不受影响
- 锁定范围与热键行为可在控制窗「防护设置」中调整，设置保存在本地（`plugin-data/input-lock/`），不上传任何数据

## 版本信息

| 版本 | 日期 | 说明 |
|------|------|------|
| 1.0.0 | 2026-09-25 | 首个版本：一键锁定 / 手势解锁 / 兜底自动解除 / 顶部横幅 / 范围与手势设置 / 全局热键 |

---

**插件 ID**: input-lock
**作者**: li_TL

---

<details>
<summary>English</summary>

# Input Lock

> An input shield for cleaning your keyboard & mouse: lock all keyboard and mouse input with one click, swallow accidental presses, keep the screen on.

## Features

- **One-click protection**: lock global keyboard & mouse input; accidental presses while wiping never reach any app, and the screen stays visible
- **Fast activation**: global hotkey `Ctrl+Alt+K` brings up the control window anytime (or search "input lock" in Quick Launcher)
- **Deliberate unlock gesture**: press `Esc ×3` within 2 seconds (default) — scattered wiping presses won't trigger it; switchable to "hold Esc 3s" or "Ctrl+Alt+F" in settings
- **Multiple auto-recovery safeguards**: forced auto-release when the hard limit is reached (30 min by default, adjustable 5-120, cannot be disabled); if the plugin exits unexpectedly, the OS restores input immediately
- **Clear status**: a top banner shows remaining time, blocked-input count, and the current unlock gesture
- **Flexible scope**: All / Keyboard only / Mouse only
- **Lock on open** (optional): with this enabled, opening via hotkey starts a cancellable 3-second countdown into protection

## Usage

1. Before cleaning, press `Ctrl+Alt+K` (or open "Input Lock" in the main window)
2. Pick a duration (Manual / 5 / 15 / 30 min) and click "Start Protection"
3. Wipe away; the top banner shows the countdown and blocked count
4. When done, perform the unlock gesture (default: `Esc ×3`)

## Notes

- `Ctrl`+`Alt`+`Del` is an OS-level secure sequence no software can intercept — it always works as the last resort
- System popups (e.g. UAC prompts) appearing during protection must be handled after unlocking
- Most touch input is blocked; a few driver-exclusive devices (some tablets, gamepads) are out of scope
- Power / sleep buttons are unaffected
- Settings are stored locally (`plugin-data/input-lock/`); nothing is uploaded

| Version | Date | Notes |
|---------|------|-------|
| 1.0.0 | 2026-09-25 | Initial release: one-click lock / gesture unlock / hard-limit auto-release / top banner / scope & gesture settings / global hotkey |

**Plugin ID**: input-lock
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
