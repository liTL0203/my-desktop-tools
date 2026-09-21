# v2.2.1 更新说明 (2026-09-16)

## 修复
- 修复市场安装的插件在侧边栏/气泡显示占位图标的问题——ZIP 现已包含插件图标文件
- 构建配置适配 pnpm v12（工程内部，不影响使用）

---

# v2.2.0 更新说明 (2026-09-16)

## 优化
- 随核心启动性能优化同步适配，细节打磨

---

# v2.1.0 更新说明 (2026-09-16)

## 新增
- 全新双栏工作台：列管理与数据预览并排，所见即所得
- 支持 CSV 导入与导出
- 错误定位：解析失败时精确提示行列位置

## 优化
- 代码质量加固

---

# v2.0.0 Release Notes (2026-09-12)

## Redesign
- New dual-pane workbench UI (Plan A): JSON source editor on the left (line numbers, syntax highlight, format/paste/sample), preview grid with sheet tabs on the right; frequent options (flatten, header style) moved to the top bar, low-frequency settings consolidated into the ⚙ advanced popover
- Column management: click any column header to rename, exclude, or override its write type (auto / text / number / date) — fixes IDs turning into scientific notation and dates staying text
- Input: drag & drop .json files, clipboard paste button, parse error located to line:col with the error line highlighted
- Export: CSV current sheet / CSV all sheets (one file per sheet, UTF-8 BOM), in addition to xlsx
- Resizable split pane (drag the divider, double-click to reset, width persisted)
- Grid ↔ editor linking: click a cell to locate its source in the JSON editor; double-click to edit the value inline and write it back (typed encoding keeps JSON valid)
- Editor horizontal viewing: wheel pans sideways after vertical ends; Alt-drag or middle-drag to pan
- Kept: QuickAction auto-fill & preview, multi-sheet auto split, nested flatten, open-after-save, light/dark theme, zh/en i18n

<details>
<summary>中文说明</summary>

# v2.0.0 更新说明 (2026-09-12)

## 重设计
- 全新双栏工作台界面（方案 A）：左侧 JSON 源（行号、语法高亮、格式化/粘贴/示例），右侧预览网格 + 底部 Sheet 标签；高频选项（嵌套展开、表头样式）移至顶栏，低频设置归拢 ⚙ 高级设置弹层
- 列管理：点列头即可重命名 / 排除 / 覆盖写入类型（自动·文本·数字·日期）——解决编号变科学计数法、日期被当文本
- 输入增强：拖拽 .json 文件、剪贴板一键粘贴、解析错误定位到行:列并高亮错误行
- 导出增强：新增 CSV 当前 Sheet / 全部 Sheet（每表一文件，UTF-8 BOM 防乱码），xlsx 保持不变
- 分栏可拖动：拖动中缝调整左右宽度（双击复位，宽度自动记忆）
- 表格 ↔ 源码联动：单击单元格定位左侧对应 JSON 位置；双击直接编辑该值并按类型写回（JSON 始终合法）
- 编辑器横向查看：长行滚轮到边后自动转横向；Alt 拖动 / 中键拖动平移
- 保留：QuickAction 自动填入预览、多数组多 Sheet、嵌套展开、保存后打开、明暗主题、中英双语

</details>

---

# v1.1.1 Release Notes (2026-08-18)

## Maintenance
- Version sync release: no functional changes; aligned with the latest marketplace icon loading optimization

<details>
<summary>中文说明</summary>

# v1.1.1 更新说明 (2026-08-18)

## 维护
- 版本同步发布：无功能性变更，与最新商城图标加载优化对齐

</details>

---

# v1.1.0 Release Notes (2026-08-17)

## Maintenance
- Added bilingual metadata (purpose/useCases/longDescription/features) via metadata.json to enrich marketplace detail display
- Version sync release: no functional changes

<details>
<summary>中文说明</summary>

# v1.1.0 更新说明 (2026-08-17)

## 维护
- 新增 metadata.json 双语元数据（purpose/useCases/longDescription/features），丰富商城详情弹窗展示
- 版本同步发布：无功能性变更

</details>

---

# v1.0.0 Release Notes (2026-08-14)

## New Features
- **JSON to Excel Conversion**: One-click conversion of JSON data into Excel spreadsheet files
- **Nested Object Expansion**: Nested objects are automatically flattened using dot notation (e.g., `user.name`), making complex data structures readable in tabular form
- **Multi-Sheet Support**: Automatically creates multiple sheets when the root object contains multiple arrays
- **Data Preview**: Table-based data preview with first N rows shown before conversion
- **Configurable Export**: Settings for header styling, empty value handling, auto column width, and external program selection
- **QuickAction Integration**: Auto-detects JSON data in the context panel and offers one-click conversion

<details>
<summary>中文说明</summary>

# v1.0.0 更新说明 (2026-08-14)

## 新增功能
- **JSON 转 Excel**：将 JSON 数据一键转换为 Excel 表格文件
- **嵌套对象展开**：嵌套对象通过 dot notation 自动扁平化展开（如 `user.name`），使复杂数据结构在表格中清晰可读
- **多 Sheet 支持**：根对象含多个数组时自动生成多个工作表
- **数据预览**：转换前提供基于表格的数据预览（显示前 N 行）
- **可配置导出**：支持表头样式、空值处理、自动列宽、外部程序选择等设置
- **QuickAction 集成**：快捷操作面板自动识别 JSON 数据并提供一键转换

</details>

---

# Changelog

## [0.1.0] - 2026-08-14

### Added
- 初始版本：JSON 数据一键转换为 Excel 表格
- 支持 QuickAction 快捷操作面板自动识别 JSON 数据
- 支持嵌套对象自动展开（dot.notation）
- 支持多 Sheet 导出（根对象含多个数组时自动分 Sheet）
- 提供数据预览功能（表格 + 前 N 行）
- 提供配置页：打开程序设置、表头样式、空值处理、自动列宽等
- 支持保存后自动使用配置的程序打开 Excel 文件
