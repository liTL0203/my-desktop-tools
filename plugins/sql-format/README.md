# SQL 美化

> 离线 SQL 文本工作台：格式化、压缩、校验、多语句导航、转换与静态分析

## 功能介绍

- **SQL 格式化**：支持 MySQL / PostgreSQL / SQLite / SQL Server (T-SQL) / Oracle (PL/SQL) 五种方言；关键字大小写、缩进、AND/OR 换行位置、运算符紧凑度、语句间空行均可配置，内置「默认 / 紧凑 / 宽松」三套预设。
- **SQL 压缩**：一键去除注释与多余空白，压成单行便于传输；字符串字面量原样保护。
- **语法校验**：括号/引号配对检查，错误定位到行；状态栏徽标实时提示。
- **多语句导航**：自动按分号拆分脚本（忽略字符串与注释里的分号），点击语句标签直接跳转。
- **转换工具**：SELECT 转 COUNT、建表 DDL 转 TypeScript 接口、INSERT 语句转 CSV / JSON。
- **静态分析**：自动提取涉及的表和字段清单，并给出常见慢查询模式提示（SELECT \*、WHERE 中的 OR、无 WHERE 的 UPDATE/DELETE、无分页的全量查询）。
- **片段库**：内置分页、UPSERT、窗口函数 TopN、按天统计等常用模板，也支持保存自己的常用 SQL。
- **历史记录**：每次格式化自动记录（本地保留 20 条），点击即可恢复。
- **文件支持**：直接打开 / 保存 .sql 文件。
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
| 0.1.0 | 2026-09-14 | 初始版本：格式化/压缩/校验/多语句导航/预设/五方言 + CodeMirror 双编辑器 + 转换/分析/片段/历史 + .sql 文件 + QuickAction 全链路（LV1-LV3） |

---

**插件 ID**: sql-format
**作者**: My Desktop Tools

---

## ⚠️ Disclaimer

- **"AS IS"**: This software is provided "AS IS", without any express or implied warranty, including but not limited to merchantability, fitness for a particular purpose, and non-infringement.
- **Use at Your Own Risk**: The developer shall not be liable for any direct or indirect losses (including but not limited to data loss, system damage, business interruption) caused by the use of this software. Users must assess and bear all risks.
- **Data Backup**: It is recommended to back up important data before using this software to prevent irreversible loss.
- **Compatibility Risks**: This software may have unknown defects or be incompatible with certain system environments, hardware configurations, or third-party software. The developer does not guarantee normal operation in all environments.
- **Plugin Disclaimer**: Plugins in this application are independent modules. The developer makes no guarantee regarding the behavior, security, or stability of third-party plugins. Users must assess and bear the risks of using third-party plugins.

> Downloading or using this software indicates that you have read and agree to the above disclaimer.
