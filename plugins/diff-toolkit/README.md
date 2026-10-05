# 内容对比工具

> 内容对比工具插件 - 万物皆可对比：文本/JSON/CSV 表格/文件夹/图片五种对比，词级定位与差异清单快速巡检

## 功能介绍

- **文本 / 代码对比**：行级 + 行内词级双层定位；**中文逐字、西文按词**精确高亮
- **三视图 + 概览标尺**：并排 / 统一 / 仅看差异；未变更区域自动折叠；右侧标尺展示差异分布，点击直达
- **差异清单**：每处差异带摘录预览（`旧值 → 新值`），点击跳转；首个 / 上一处 / 下一处巡检
- **忽略规则**：行尾/全部空白、大小写三档 + **正则规则**（如忽略注释行、时间戳字段）+ **数值容差**（阈值内数值视为相同），实时重算
- **JSON 结构对比**：键顺序无关、识别数组重排（⇄）、类型变化标注；树视图 ⇄ 原文切换；非法 JSON 自动回退
- **CSV 表格对比**：按键列对齐（顺序无关），单元格级 旧值→新值，列头变化计数，仅差异行过滤
- **文件夹对比**：递归对比两目录，快速（大小+时间）或内容校验（SHA-256）两种模式，状态过滤与汇总；文本文件点击即下钻到行级对比
- **图片对比**：并排 / 滑动分隔线 / 叠加渐变 / 差异混合（相同区域变黑只发光差异）四种模式，附差异像素比例
- **导出报告**：一键导出自包含 HTML 报告（统计+清单+明细），双击即看、无需安装
- **QuickAction**：任意位置选中文本 → 与剪贴板一键对比（预览卡直接显示统计），或设为对比左/右侧
- **统计与性能**：`+新增 −删除 ~修改` 与相似度；虚拟滚动支撑数万行；本地 Rust 计算，内容不出本机

## 使用方法

1. 打开 My Desktop Tools，进入「内容对比工具」
2. 文本/JSON/表格页签：左右两栏粘贴 / 拖入内容（或「打开文件」）；文件夹页签：输入或选择两个目录；图片页签：拖入两张图片
3. 点击对比按钮（或 Ctrl+Enter）；开启「实时对比」后修改自动重算
4. 用差异清单、概览标尺或巡检按钮逐处检查；工具栏「规则」里配置正则忽略与数值容差
5. 在任意应用选中一段文本，快捷操作面板里点「文本对比」即可与剪贴板比对

## 注意事项

- 文本单侧上限 10MB / 50000 行；文件夹上限 20000 条目（超大树可用过滤缩小）
- 文件读取按 UTF-8；其他编码文本可能乱码；「内容校验」模式对大目录耗时较长（逐文件哈希）
- 图片对比为纯前端处理，单图 ≤20MB；两图尺寸不同时按左图尺寸缩放比较并提示
- 视图/规则/容差等偏好自动保存；对比结果不落盘，输入内容不会上传到任何地方


## 版本信息

| 版本 | 日期 | 说明 |
|------|------|------|
| 1.2.0 | 2026-10-05 | 竞品对标大版本：中文词级修复、概览标尺、虚拟滚动、正则忽略规则+数值容差、CSV 表格对比、文件夹对比、图片对比、HTML 报告导出、QuickAction 与剪贴板对比 |
| 1.1.0 | 2026-09-25 | 维护性同步 |
| 1.0.0 | 2026-09-19 | 首发上架：文本行级+词级对比、三视图、差异清单、忽略规则、JSON 结构对比、偏好持久化 |

---

<details>
<summary>English</summary>

# Content Diff Tool

> diff-toolkit plugin - Compare anything, not just code: text, JSON, CSV tables, folders and images, with word-level highlights and a jumpable change list.

## Features

- **Text / code diff**: line-level plus word-level highlights; CJK characters marked one by one, western text word by word
- **Three views + overview rail**: side-by-side, unified, changes-only; unchanged regions auto-fold; a rail on the right shows the difference distribution, click to jump
- **Change list**: every difference with an excerpt preview (`old → new`); first / previous / next navigation
- **Ignore rules**: trailing / all whitespace, letter case, plus **regex rules** (comment lines, timestamp fields) and **numeric tolerance**; recomputed instantly
- **JSON structure diff**: key order irrelevant, array reordering detected (⇄), type changes flagged; tree ⇄ raw views; invalid JSON falls back automatically
- **CSV table diff**: rows aligned by the key column (order independent), cell-level old → new, per-column change counts, changed-rows filter
- **Folder diff**: recursively compare two folders in quick (size + mtime) or content-check (SHA-256) mode, with status filters and summaries; click a text file to drill into its line diff
- **Image diff**: side-by-side, swipe divider, fade blend, and difference blend (identical pixels turn black); diff-pixel ratio included
- **Report export**: one click to a self-contained HTML report (stats + change list + details), opens anywhere without installation
- **QuickAction**: select text anywhere and compare it against the clipboard in one click (preview card shows the stats), or set it as either side
- **Statistics & performance**: `+added −deleted ~modified` and similarity; virtual scrolling handles tens of thousands of lines; fully local Rust engine

## Usage

1. Open My Desktop Tools and go to the content diff tool
2. Text/JSON/table tabs: paste or drop content into both panes (or Open File); folder tab: enter or pick two directories; image tab: drop two images
3. Press compare (or Ctrl+Enter); with Live enabled, edits recompute automatically
4. Inspect differences via the change list, the overview rail, or the navigation buttons; configure regex rules and numeric tolerance in the Rules popover
5. Select text in any app and use "文本对比" in the QuickAction panel to compare against the clipboard

## Notes

- Text per-side limit: 10MB / 50,000 lines; folders cap at 20,000 entries (use filters on huge trees)
- Files are read as UTF-8; other encodings may look garbled; content-check mode is slower on large trees (per-file hashing)
- Image compare is pure frontend, ≤20MB per image; different dimensions are scaled to the left image's size with a notice
- Preferences are remembered; results are never written to disk and inputs are never uploaded

| Version | Date | Notes |
|---------|------|-------|
| 1.2.0 | 2026-10-05 | Competitor-parity release: CJK word-level fix, overview rail, virtual scrolling, regex rules + numeric tolerance, CSV table diff, folder diff, image diff, HTML report export, QuickAction clipboard compare |
| 1.1.0 | 2026-09-25 | Maintenance sync |
| 1.0.0 | 2026-09-19 | Initial release: text diff (line + word), three views, change list, ignore rules, JSON structure diff, persisted preferences |

</details>

---

## ⚠️ Disclaimer

- **"AS IS"**: This software is provided "AS IS", without any express or implied warranty, including but not limited to merchantability, fitness for a particular purpose, and non-infringement.
- **Use at Your Own Risk**: The developer shall not be liable for any direct or indirect losses (including but not limited to data loss, system damage, business interruption) caused by the use of this software. Users must assess and bear all risks.
- **Data Backup**: It is recommended to back up important data before using this software to prevent irreversible loss.
- **Compatibility Risks**: This software may have unknown defects or be incompatible with certain system environments, hardware configurations, or third-party software. The developer does not guarantee normal operation in all environments.
- **Plugin Disclaimer**: Plugins in this application are independent modules. The developer makes no guarantee regarding the behavior, security, or stability of third-party plugins. Users must assess and bear the risks of using third-party plugins.

> Downloading or using this software indicates that you have read and agree to the above disclaimer.
