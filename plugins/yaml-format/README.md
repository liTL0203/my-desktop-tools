# YAML 格式化 v0.1.0

离线 YAML 工作台：格式化、校验定位、压缩、JSON 互转、扁平化与多文档处理，专为 K8s 清单与 CI 配置场景设计。所有处理均在本地完成，无网络请求。

## 功能介绍

- **格式化 / 校验**：整理缩进与对齐；语法错误精确到行列并高亮上下文；Tab 缩进这类常见粘贴错误单独提示
- **注释保留**：默认往返排版时保留 `#` 注释与键顺序（可关闭获得纯数据重排）；可选按键名排序
- **YAML ⇄ JSON**：双向互转，一键交换输入与结果
- **扁平化**：嵌套结构展开为 `server.port` / `users[0].name` 点号键值表，一键复制 .env 风格文本
- **多文档**：按 `---` 切分的 K8s 多资源文件逐文档校验、查看与复制，标注各文档起始行
- **QuickAction 联动**：任意应用选中 YAML 按鼠标中键，面板直接显示校验结论卡（结构统计 / K8s kind / 错误行列定位），Enter 打开插件自动载入；右键菜单可直达格式化 / 转 JSON / 扁平化 / 多文档
- **文件与偏好**：打开 .yaml/.yml/.json 文件、保存结果；缩进/行宽/注释/排序等选项自动记忆

## 使用说明

1. 主窗口使用：粘贴或打开文件后自动格式化；顶部页签切换四种功能；底部状态栏实时显示校验结论与统计
2. QuickAction 使用：在任意应用选中 YAML 文本 → 鼠标中键 → 面板出现本插件校验卡 → Enter 打开
3. 快捷键：Ctrl+S 复制结果；Ctrl+B 折叠侧栏（核心约定）；分栏可拖拽（双击复位）

## 注意事项

- 文本处理上限 10MB（文件）/ 5MB（编辑器），超限会提示
- 扁平化以数据值为准（注释不参与）；数组下标以 `[0]` 形式呈现
- 多文档切分按 `---` 独立行识别；块标量内的 `---` 属于极端场景，完整语义以格式化结果为准

## 版本信息

- v0.1.0（2026-09-16）：首个版本

---

<details>
<summary>English</summary>

# YAML Formatter v0.1.0

> Offline YAML workbench: formatting, validation with error locating, minification, JSON conversion, flattening, and multi-document processing — designed for K8s manifests and CI configuration scenarios. All processing is done locally with no network requests.

## Features

- **Format / Validate**: Normalizes indentation and alignment; syntax errors are pinpointed to line and column with context highlighting; common paste mistakes such as Tab indentation are reported separately
- **Comment preservation**: By default, round-trip formatting keeps `#` comments and key order (turn it off for pure data reordering); optional sorting by key name
- **YAML ⇄ JSON**: Two-way conversion with one-click swap of input and result
- **Flatten**: Expands nested structures into a dot-notation key-value table such as `server.port` / `users[0].name`, with one-click copy as .env-style text
- **Multi-document**: K8s multi-resource files split by `---` are validated, viewed, and copied document by document, with each document's starting line annotated
- **QuickAction integration**: Select YAML in any app and press the middle mouse button — the panel shows a validation result card (structure stats / K8s kind / error line-column location) right away; press Enter to open the plugin with the text loaded; the context menu jumps straight to format / convert to JSON / flatten / multi-document
- **Files & preferences**: Open .yaml/.yml/.json files and save results; options such as indent width, line width, comments, and sorting are remembered automatically

## Usage

1. Main window: paste or open a file and it is formatted automatically; switch between the four functions via the top tabs; the bottom status bar shows validation results and statistics in real time
2. QuickAction: select YAML text in any app → middle mouse button → the plugin's validation card appears in the panel → press Enter to open
3. Shortcuts: Ctrl+S copies the result; Ctrl+B collapses the side panel (core convention); the split panes are draggable (double-click to reset)

## Notes

- Text processing limits: 10MB (file) / 5MB (editor); a warning appears when exceeded
- Flattening is based on data values only (comments are not included); array indexes are shown as `[0]`
- Multi-document splitting recognizes `---` only on standalone lines; `---` inside block scalars is an edge case — the formatted result is authoritative for full semantics

## Version History

- v0.1.0 (2026-09-16): Initial release

</details>

---

## ⚠️ Disclaimer

- **"AS IS"**: This software is provided "AS IS", without any express or implied warranty, including but not limited to merchantability, fitness for a particular purpose, and non-infringement.
- **Use at Your Own Risk**: The developer shall not be liable for any direct or indirect losses (including but not limited to data loss, system damage, business interruption) caused by the use of this software. Users must assess and bear all risks.
- **Data Backup**: It is recommended to back up important data before using this software to prevent irreversible loss.
- **Compatibility Risks**: This software may have unknown defects or be incompatible with certain system environments, hardware configurations, or third-party software. The developer does not guarantee normal operation in all environments.
- **Plugin Disclaimer**: Plugins in this application are independent modules. The developer makes no guarantee regarding the behavior, security, or stability of third-party plugins. Users must assess and bear the risks of using third-party plugins.

> Downloading or using this software indicates that you have read and agree to the above disclaimer.
