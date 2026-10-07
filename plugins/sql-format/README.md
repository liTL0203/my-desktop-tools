# SQL 美化

> 离线 SQL 文本工作台：格式化、压缩、校验、多语句导航、转换与静态分析

## 功能介绍

- **SQL 格式化**：支持 19 种方言（按关系型经典 / 分析数仓 / 企业与其他分组：MySQL、MariaDB、TiDB、PostgreSQL、SQLite、SQL Server、Oracle、BigQuery、Snowflake、Redshift、ClickHouse、Trino、Hive、Spark、SingleStoreDB、Db2、N1QL、标准 SQL 等）；关键字/数据类型/函数名大小写、缩进、AND/OR 换行位置、行宽上限、运算符紧凑度、分号位置、语句间空行均可配置，内置「默认 / 紧凑 / 宽松」三套预设，且支持**每个方言记忆一套专属风格**。
- **SQL 压缩**：一键去除注释与多余空白，压成单行便于传输；字符串字面量原样保护。
- **语法校验**：括号/引号配对检查，错误定位到行；状态栏徽标实时提示。
- **多语句导航**：自动按分号拆分脚本（忽略字符串与注释里的分号），点击语句标签直接跳转。
- **局部保护**：用 `[noformat]…[/noformat]` 包住的代码块在格式化/压缩时原样保留（手写对齐不被重排），`[minify]…[/minify]` 包住的代码块则单独压缩。
- **选中大小写转换**：输入框选中片段后点 AA / aa / Aa 一键转换。
- **转换工具**：SELECT 转 COUNT、建表 DDL 转 TypeScript 接口、INSERT 语句转 CSV / JSON、SQL 转 Python / Java / TypeScript 宿主语言字符串（自动转义）。
- **静态分析**：自动提取涉及的表和字段清单，并给出常见慢查询模式提示（SELECT \*、WHERE 中的 OR、无 WHERE 的 UPDATE/DELETE、无分页的全量查询）。
- **片段库**：内置分页、UPSERT、窗口函数 TopN、按天统计等常用模板，也支持保存自己的常用 SQL。
- **历史记录**：每次格式化自动记录（本地保留 20 条），点击即可恢复。
- **文件支持**：直接打开 / 保存 .sql 文件。
- **AI 助手**：解释 SQL / 优化建议 / 修复建议 / 自然语言转 SQL（经核心 AI 网关调用你配置的模型；使用前有明确的出网确认提示；未配置 AI 时给出指引）。
- **QuickAction**：在任意应用中选中文本按中键（或右键菜单），识别为 SQL 后可一键拉起本插件格式化，还能在未打开插件时预览语句统计。

## 使用说明

1. 打开 My Desktop Tools，进入「SQL 美化」页面（或从独立窗口 / QuickAction 打开）。
2. 将 SQL 粘贴到左侧输入框，点击「格式化」按钮，右侧即刻显示美化结果。
3. 需要修改风格时，点击右上角 ⚙ 图标调整格式选项，或切换顶部的预设与方言。
4. 点击「压缩」得到单行 SQL；点击「校验」查看语法问题及所在行。
5. 打开右侧面板按钮（▣）可使用分析、转换、片段库和历史记录。
6. 结果面板顶部可「复制」或「保存 .sql」；输入面板可从文件导入。
7. 开启状态栏的「实时格式化」后，输入时自动同步格式化结果。

## 注意事项

- 本插件**完全离线运行**，不会连接任何数据库，也不会上传你的 SQL 内容；所有设置、片段、历史仅保存在本机。
- 输入上限 2MB；打开的 .sql 文件上限 10MB，超大脚本请先拆分。
- 语法校验是括号/引号级别的快速检查，不能替代数据库的完整语法解析；格式化报错信息可作为进一步排障参考。
- 压缩与格式化不会改动字符串内的内容；请勿在 SQL 字符串中手工写入伪造的注释符号边界。

## 版本信息

| 版本 | 日期 | 说明 |
|------|------|------|
| 1.3.0 | 2026-10-05 | 竞品对标轮：19 方言 + 选项补齐（行宽/类型函数大小写/分号行）+ [noformat]/[minify] 局部保护 + 选中大小写转换 + SQL→Python/Java/TS 转义 + 按方言记忆选项 + AI 四件套（解释/优化/修复/自然语言转 SQL） |
| 0.1.0 | 2026-09-14 | 初始版本：格式化/压缩/校验/多语句导航/预设/五方言 + CodeMirror 双编辑器 + 转换/分析/片段/历史 + .sql 文件 + QuickAction 全链路（LV1-LV3） |

---

**插件 ID**: sql-format
**作者**: My Desktop Tools

---

<details>
<summary>English</summary>

# SQL Format

> Offline SQL text workbench: formatting, minification, validation, multi-statement navigation, transformation, and static analysis

## Features

- **SQL formatting**: supports five dialects — MySQL / PostgreSQL / SQLite / SQL Server (T-SQL) / Oracle (PL/SQL); keyword casing, indentation, AND/OR line-break position, operator compactness, and blank lines between statements are all configurable, with three built-in presets: "Default / Compact / Relaxed".
- **SQL minification**: remove comments and redundant whitespace in one click and compress the script into a single line for easy transfer; string literals are protected as-is.
- **Syntax validation**: bracket/quote pairing checks with errors located down to the line; real-time hints via the status bar badge.
- **Multi-statement navigation**: the script is automatically split by semicolons (semicolons inside strings and comments are ignored); click a statement tab to jump straight to it.
- **Conversion tools**: SELECT to COUNT, table DDL to TypeScript interface, INSERT statements to CSV / JSON.
- **Static analysis**: automatically extracts the list of involved tables and columns and flags common slow-query patterns (SELECT \*, OR in WHERE, UPDATE/DELETE without WHERE, unpaginated full-table queries).
- **Snippet library**: built-in templates for common cases such as pagination, UPSERT, window-function Top-N, and per-day statistics; you can also save your own frequently used SQL.
- **History**: every formatting run is recorded automatically (last 20 kept locally); click to restore.
- **File support**: open / save .sql files directly.
- **QuickAction**: select text in any app and press the middle mouse button (or use the right-click menu); once recognized as SQL, this plugin can be launched for one-click formatting, and statement statistics can be previewed even when the plugin is not open.

## Usage

1. Open My Desktop Tools and go to the "SQL Format" page (or open it from the standalone window / QuickAction).
2. Paste SQL into the left input box and click the "Format" button; the beautified result appears on the right instantly.
3. To adjust the style, click the ⚙ icon at the top right to change format options, or switch the preset and dialect at the top.
4. Click "Minify" to get single-line SQL; click "Validate" to see syntax issues and the lines they occur on.
5. Open the right panel button (▣) to use analysis, conversion, the snippet library, and history.
6. The top of the result panel offers "Copy" or "Save .sql"; the input panel can import from a file.
7. With "Live formatting" enabled in the status bar, the formatting result syncs automatically as you type.

## Notes

- This plugin **runs completely offline**: it never connects to any database and never uploads your SQL content; all settings, snippets, and history are saved only on this machine.
- Input is limited to 2MB; opened .sql files are limited to 10MB — split overly large scripts first.
- Syntax validation is a quick bracket/quote-level check and cannot replace the database's full syntax parsing; formatting error messages can serve as a reference for further troubleshooting.
- Minification and formatting never change content inside strings; do not hand-write fake comment-symbol boundaries inside SQL strings.

## Version History

| Version | Date | Notes |
|---------|------|-------|
| 0.1.0 | 2026-09-14 | Initial release: formatting/minify/validate/multi-statement navigation/presets/five dialects + CodeMirror dual editors + conversion/analysis/snippets/history + .sql files + full QuickAction pipeline (LV1-LV3) |

</details>

---

## ⚠️ Disclaimer

- **"AS IS"**: This software is provided "AS IS", without any express or implied warranty, including but not limited to merchantability, fitness for a particular purpose, and non-infringement.
- **Use at Your Own Risk**: The developer shall not be liable for any direct or indirect losses (including but not limited to data loss, system damage, business interruption) caused by the use of this software. Users must assess and bear all risks.
- **Data Backup**: It is recommended to back up important data before using this software to prevent irreversible loss.
- **Compatibility Risks**: This software may have unknown defects or be incompatible with certain system environments, hardware configurations, or third-party software. The developer does not guarantee normal operation in all environments.
- **Plugin Disclaimer**: Plugins in this application are independent modules. The developer makes no guarantee regarding the behavior, security, or stability of third-party plugins. Users must assess and bear the risks of using third-party plugins.

> Downloading or using this software indicates that you have read and agree to the above disclaimer.
