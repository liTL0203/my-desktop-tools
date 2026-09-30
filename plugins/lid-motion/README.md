# 合盖动效

把折叠屏手机的合盖仪式感带进 Windows 笔记本：合上/打开盖子时，屏幕上播放「凝霜入眠」「破晓展开」等同源质感的转场动画（灵感来自 iPhone Duo 折叠转场：画面定影不缩放、渐进凝霜、向转轴折入黑暗、全程无黑帧）。

## 功能

- **七个转场效果**（合盖：凝霜入眠/星尘归仓/复古关机/伙伴入眠；开盖：破晓展开/涟漪苏醒/伙伴迎接），全部基于合盖瞬间的真实屏幕冻结画面
- **接管合盖行为**：合盖不再睡眠、动画才可见；AC/DC 原值自动备份，停用/还原一键恢复，插件异常退出后下次启动自动核对自愈
- **无外接屏自动入睡兜底**：合盖后若无活动显示器，按设定延时（1-30 分钟，默认 5）自动入睡，防止在包里持续发热
- **电池感知**：可设「仅接通电源时接管」，电池供电保持系统默认行为
- **手动预览**：设置页一键在屏幕上走完整播放管线，不用真合盖即可查看效果
- **台式机自动降级**：无合盖动作设置的机器不接管任何策略，仅保留预览
- 明暗双主题；中英双语

## 使用方法

1. 安装后插件随核心自启（需监听合盖事件）
2. 打开「合盖动效」设置页，确认「接管合盖行为」开启（默认开启）
3. 点「预览合盖 / 预览开盖」挑选喜欢的效果
4. 接外接屏时合上笔记本 → 外接屏播放合盖动画，机器保持唤醒；单屏时打开盖子 → 内屏播放开盖动画

## 注意事项

- 合盖动画的可见前提是「合盖=不操作」（本插件的接管即是做此修改并记录原值；随时可还原）
- 合盖瞬间笔记本内屏被物理遮挡，因此合盖动画播在外接屏（若为副屏则暂不播，v0.1 覆盖层仅主屏）；开盖动画播在内屏
- 若系统设置了开盖需密码，开盖动画会在解锁后才可能可见（Windows 安全桌面限制）
- 冻结画面仅存内存并在 60 秒后自动清除，不会写入磁盘或日志

## 版本信息

| 版本 | 日期 | 说明 |
|------|------|------|
| 0.1.0 | 2026-09-30 | 首个开发版：七效果全量、策略接管/还原/自愈、延时入睡、预览、双语主题 |

---

<details>
<summary>English</summary>

# Lid Motion

Bring the foldable-phone close ritual to your Windows laptop: when you close or open the lid, a Duo-style transition animation plays on screen (frozen frame, progressive frost, folding into the hinge, no black frames — inspired by the iPhone Duo fold transition).

## Features

- **Seven transitions** (closing: Frost Fade / Stardust / Retro CRT / Sleepy Pet; opening: Dawn Unfold / Ripple Wake / Pet Greeting), all rendered over a real frozen frame of your screen at the moment of closing/opening
- **Lid policy takeover**: closing the lid no longer sleeps (that's what makes the animation visible). Original AC/DC values are backed up, restorable in one click, and self-healed on next launch after abnormal exit
- **Auto-sleep fallback**: with no external display attached, the machine auto-sleeps after a configurable delay (1-30 min, default 5) so it never runs hot in a bag
- **Battery aware**: optional "only take over on AC power" keeps system default behavior on battery
- **Manual preview**: walk the full pipeline from the settings page — no need to actually close the lid
- **Graceful desktop degradation**: machines without a lid-action setting take over nothing
- Light/dark themes; English & Chinese

## How to use

1. The plugin auto-starts with the core (it must listen for lid events)
2. Open the Lid Motion settings page and keep "Take over lid behavior" on (default)
3. Use "Preview closing / opening" to pick your favorite effects
4. Docked: close the lid and watch the closing animation on the external display (machine stays awake); solo: open the lid and enjoy the opening animation

## Notes

- The closing animation requires "lid close = do nothing" (that's exactly what the takeover does, with the original value recorded and restorable)
- At the moment of closing, the internal panel is physically hidden, so the closing animation plays on the external display (secondary displays are not covered in v0.1 — overlay is primary-only); the opening animation plays on the internal display
- If Windows requires a password on wake, the opening animation is only visible after unlock (secure-desktop limitation)
- Frozen frames live in memory only and are purged after 60 seconds — never written to disk or logs

| Version | Date | Notes |
|---------|------|-------|
| 0.1.0 | 2026-09-30 | First dev release: all seven effects, policy takeover/restore/self-heal, delayed auto-sleep, preview, bilingual themes |

</details>

---

## ⚠️ Disclaimer

- **"AS IS"**: This software is provided "AS IS", without any express or implied warranty, including but not limited to merchantability, fitness for a particular purpose, and non-infringement.
- **Use at Your Own Risk**: The developer shall not be liable for any direct or indirect losses (including but not limited to data loss, system damage, business interruption) caused by the use of this software. Users must assess and bear all risks.
- **Data Backup**: It is recommended to back up important data before using this software to prevent irreversible loss.
- **Compatibility Risks**: This software may have unknown defects or be incompatible with certain system environments, hardware configurations, or third-party software. The developer does not guarantee normal operation in all environments.
- **Plugin Disclaimer**: Plugins in this application are independent modules. The developer makes no guarantee regarding the behavior, security, or stability of third-party plugins. Users must assess and bear the risks of using third-party plugins.

> Downloading or using this software indicates that you have read and agree to the above disclaimer.
