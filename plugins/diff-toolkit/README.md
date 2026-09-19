# 内容对比工具

> 内容对比工具插件 - 万物皆可对比：文本/代码行级+词级对比、JSON 结构感知对比，差异清单快速定位

## 功能介绍

- **文本 / 代码对比**：行级 + 行内词级双层定位，不仅告诉你哪行变了，还精确到哪个词
- **三视图**：并排对比 / 统一视图 / 仅看差异，未变更区域自动折叠
- **差异清单**：每处差异带摘录预览（`旧值 → 新值`），点击跳转定位；上一处 / 下一处顺向巡检
- **忽略规则**：忽略行尾空白 / 忽略全部空白 / 忽略大小写，实时重算（统计与相似度同步刷新）
- **JSON 结构对比**：按键路径比较而非按行硬比——键顺序无关、识别数组重排（⇄）、类型变化标注；树视图 ⇄ 原文对比随时切换；非法 JSON 自动回退文本对比
- **统计徽章**：`+新增 −删除 ~修改` 与相似度百分比，一眼判断改动幅度
- **输入三通道**：粘贴、拖拽文本文件（≤10MB）、系统文件对话框；一键交换左右
- **本地计算**：diff 引擎全部在本地 Rust 进程完成，内容不出本机

## 使用方法

1. 打开 My Desktop Tools，进入「内容对比工具」
2. 在左右两栏分别粘贴 / 拖入要比对的内容（或点「打开文件」选择文本文件）
3. 点击中间的对比按钮（或按 Ctrl+Enter）；开启「实时对比」后修改内容自动重算
4. 用右侧差异清单或上一处 / 下一处按钮巡检每一处不同
5. 粘贴 JSON 内容并切到「JSON 对比」页签，可获得结构树对比

## 注意事项

- 单侧输入上限 10MB / 50000 行，超出会明确提示
- 文件读取按 UTF-8 编码；其他编码的文本可能出现乱码（建议先转存 UTF-8）
- 视图模式、忽略规则、实时开关等偏好会自动保存，重启后保留
- 对比结果不落盘，关闭插件即清空；输入内容不会上传到任何地方

## 版本信息

| 版本 | 日期 | 说明 |
|------|------|------|
| 0.1.0 | 2026-09-19 | 初始版本：文本行级+词级对比、三视图、差异清单、忽略规则、JSON 结构对比、偏好持久化 |

---

<details>
<summary>English</summary>

# Content Diff Tool

> diff-toolkit plugin - Compare anything, not just code: line + word level text diff, JSON structure-aware diff, and a jumpable change list.

## Features

- **Text / code diff**: line-level plus in-line word-level highlights, down to the exact changed word
- **Three views**: side-by-side, unified, and changes-only; unchanged regions auto-fold
- **Change list**: every difference with an excerpt preview (`old → new`); click to jump, step through with previous / next
- **Ignore rules**: ignore trailing whitespace / all whitespace / letter case, recomputed instantly with stats refreshed
- **JSON structure diff**: compares by key path instead of raw lines — key order irrelevant, array reordering detected (⇄), type changes flagged; switch between tree and raw text views; invalid JSON falls back to text diff automatically
- **Statistics**: `+added −deleted ~modified` badges and a similarity percentage
- **Three input channels**: paste, drop a text file (≤10MB), or the system file dialog; one-click side swap
- **Fully local**: the diff engine runs in a local Rust process; nothing leaves your machine

## Usage

1. Open My Desktop Tools and go to the content diff tool
2. Paste or drop content into the left and right panes (or use Open File)
3. Press the compare button in the middle (or Ctrl+Enter); with Live enabled, edits recompute automatically
4. Inspect each difference via the change list or the previous / next buttons
5. Paste JSON and switch to the JSON tab for the structure tree comparison

## Notes

- Per-side limit: 10MB / 50,000 lines
- Files are read as UTF-8; other encodings may look garbled
- View mode, ignore rules and the live switch are remembered across restarts
- Results are never written to disk and inputs are never uploaded

| Version | Date | Notes |
|---------|------|-------|
| 0.1.0 | 2026-09-19 | Initial release: text diff (line + word), three views, change list, ignore rules, JSON structure diff, persisted preferences |

</details>

---

## ⚠️ Disclaimer

- **"AS IS"**: This software is provided "AS IS", without any express or implied warranty, including but not limited to merchantability, fitness for a particular purpose, and non-infringement.
- **Use at Your Own Risk**: The developer shall not be liable for any direct or indirect losses (including but not limited to data loss, system damage, business interruption) caused by the use of this software. Users must assess and bear all risks.
- **Data Backup**: It is recommended to back up important data before using this software to prevent irreversible loss.
- **Compatibility Risks**: This software may have unknown defects or be incompatible with certain system environments, hardware configurations, or third-party software. The developer does not guarantee normal operation in all environments.
- **Plugin Disclaimer**: Plugins in this application are independent modules. The developer makes no guarantee regarding the behavior, security, or stability of third-party plugins. Users must assess and bear the risks of using third-party plugins.

> Downloading or using this software indicates that you have read and agree to the above disclaimer.
