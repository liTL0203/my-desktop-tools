# 番茄钟

> 专注-休息循环节奏器：模式预设、任务绑定、休息引导、专注洞察

## 功能

- **节奏预设**：经典 25+5、深度 50+10、自定义时长，胶囊一键切换（快捷键 1/2/3）
- **任务绑定**：任务清单带预计番茄数与进度点，「专注此任务」一键启动，投入分钟自动累计
- **休息引导**：短休默认 20-20-20 护眼提示，长休默认 4-4-6 呼吸动画
- **分心记事本**：专注中想起别的事随手记下（不打断计时），休息时逐条处理
- **专注洞察**：连续天数与最佳纪录、12 周专注热力图、24 小时时段分布（黄金时段）、任务投入排行
- **音景**：雨声 / 壁炉 / 咖啡馆（Web Audio 实时合成，无音频文件），可设专注时自动播放
- **智能提醒**：阶段完成提示音、最后 10 秒滴答；窗口关闭时由后台系统提示音兜底
- **严格模式**：专注中不可暂停（只能放弃本轮且不计入统计），助力自律训练
- **数据导出**：全部专注记录导出为 CSV / JSON

## 使用方法

1. 打开 My Desktop Tools，进入「番茄钟」页面
2. 顶部切换 专注 / 任务 / 统计 三个视图，右上角齿轮进入设置
3. 在「任务」视图添加任务（可设预计番茄数），点任务行的「专注此任务」直接开始
4. 专注视图按空格开始/暂停；S 跳过阶段；E 提前完成本轮
5. 阶段结束自动衔接（进休息默认开启，回专注可按需开启）
6. 在「统计」视图查看热力图/时段分布/任务排行，并可导出数据

## 注意事项

- 所有数据存储在本地，不会上传到任何服务器
- 计时采用墙钟基准：系统睡眠/休眠唤醒后进度与真实时间一致
- 提示音与音景在插件窗口打开时生效；窗口关闭时阶段切换由系统提示音提醒
- 数据按月分片存储于插件数据目录；旧版（v2）数据保留为 .v2.bak 备份，不迁移
- 支持亮色/暗色主题，跟随主程序自动切换；支持中英文界面

## 版本信息

| 版本 | 日期 | 说明 |
|------|------|------|
| 3.0.0 | 2026-09-26 | v3 重设计：节奏预设、任务绑定、休息引导、分心记事本、专注洞察（热力图/时段分布/连续天数/任务排行）、合成音景、严格模式、墙钟计时、系统音兜底、数据导出与按月分片；存储格式换代（v2 数据自动备份不迁移） |
| 2.4.0 | 2026-09-25 | 依赖升级与工程同步 |
| 2.0.0 | 2026-04-01 | 独立插件版本：双主题、自动短/长休息切换、本地统计 |

---

<details>
<summary>English</summary>

# Pomodoro

> A focus rhythm tool: mode presets, task binding, guided breaks, and focus insights.

## Features

- **Rhythm presets**: Classic 25+5, Deep 50+10, and Custom durations, one-click switching (keys 1/2/3)
- **Task binding**: task list with estimated pomodoros and progress dots; "Focus on this" starts instantly; minutes accumulate per task
- **Guided breaks**: 20-20-20 eye rest on short breaks, 4-4-6 breathing animation on long breaks
- **Distraction pad**: capture stray thoughts mid-focus (without breaking the timer), resolve them on break
- **Focus insights**: streak and best record, 12-week heatmap, 24-hour distribution (golden hours), task ranking
- **Ambience**: rain / fireplace / cafe, synthesized in real time with Web Audio (no audio files); optional autoplay during focus
- **Smart reminders**: phase-completion chime, last-10-second tick; a system beep fallback covers phase changes while the window is closed
- **Strict mode**: pausing disabled during focus (abandon only, uncounted) for discipline training
- **Data export**: all sessions exportable as CSV / JSON

## How to use

1. Open My Desktop Tools and go to the Pomodoro page
2. Switch between Focus / Tasks / Stats views at the top; open settings via the gear icon
3. Add tasks in the Tasks view (with estimated pomodoros); click "Focus on this" to start
4. Press Space to start/pause; S to skip; E to finish the round early
5. Phases chain automatically (entering breaks is on by default; starting the next round is optional)
6. Review heatmap / hourly distribution / task ranking in Stats, and export your data

## Notes

- All data is stored locally; nothing is uploaded
- Wall-clock based timing stays accurate across system sleep/hibernate
- Chimes and ambience work while the plugin window is open; closed-window phase changes are covered by the system beep
- Sessions are stored in monthly shards; legacy v2 data is kept as a .v2.bak backup (not migrated)
- Light/dark themes follow the host app; Chinese and English UI supported

| Version | Date | Notes |
|---------|------|-------|
| 3.0.0 | 2026-09-26 | v3 redesign: presets, task binding, guided breaks, distraction pad, insights (heatmap/hourly/streak/ranking), synthesized ambience, strict mode, wall-clock timing, beep fallback, export and monthly sharding; storage format replaced (v2 data backed up, not migrated) |
| 2.4.0 | 2026-09-25 | Dependency upgrades and engineering sync |
| 2.0.0 | 2026-04-01 | Standalone plugin: dual themes, auto break switching, local stats |

</details>

---

## ⚠️ Disclaimer

- **"AS IS"**: This software is provided "AS IS", without any express or implied warranty, including but not limited to merchantability, fitness for a particular purpose, and non-infringement.
- **Use at Your Own Risk**: The developer shall not be liable for any direct or indirect losses (including but not limited to data loss, system damage, business interruption) caused by the use of this software. Users must assess and bear all risks.
- **Data Backup**: It is recommended to back up important data before using this software to prevent irreversible loss.
- **Compatibility Risks**: This software may have unknown defects or be incompatible with certain system environments, hardware configurations, or third-party software. The developer does not guarantee normal operation in all environments.
- **Plugin Disclaimer**: Plugins in this application are independent modules. The developer makes no guarantee regarding the behavior, security, or stability of third-party plugins. Users must assess and bear the risks of using third-party plugins.

> Downloading or using this software indicates that you have read and agree to the above disclaimer.
