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
