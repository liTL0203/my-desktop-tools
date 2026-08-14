# JSON 转 Excel

将 JSON 数据一键转换为 Excel 表格文件，支持嵌套展开、多 Sheet 导出、数据预览。

## 功能特性

- **快捷操作集成**：选中任意 JSON 文本，通过 QuickAction 面板一键启动转换
- **嵌套自动展开**：`{"user":{"name":"Tom"}}` 自动拍平为 `user.name` 列
- **多 Sheet 导出**：根对象含多个数组字段时，每个数组自动成为独立工作表
- **数据预览**：转换前可预览表头和前 N 行数据
- **配置灵活**：表头样式、空值处理、列宽自适应、打开程序等均可配置
- **保存后打开**：保存成功后可自动使用 Excel / WPS 等程序打开文件

## 使用方法

### 方式一：快捷操作（推荐）

1. 在任意应用中选中 JSON 文本
2. 触发快捷操作（鼠标中键或快捷键）
3. 在弹出的面板中选择「转为 Excel」
4. 插件窗口自动打开，JSON 数据已填入
5. 点击「保存为 Excel」按钮，选择保存位置
6. 文件保存成功后自动打开（可在配置中关闭）

### 方式二：直接打开

1. 从首页或快捷启动中打开「JSON 转 Excel」
2. 在输入框中粘贴或输入 JSON 数据
3. 预览数据无误后点击「保存为 Excel」

## 配置项

| 配置项 | 说明 | 默认值 |
|--------|------|--------|
| 保存后打开 | 保存成功后自动使用 Excel 程序打开文件 | 开启 |
| 打开程序路径 | 打开 Excel 所用程序路径，留空使用系统默认 | 空 |
| 工作表名称 | 默认工作表名称 | Sheet1 |
| 嵌套展开 | 自动展开嵌套对象为 dot.notation 列 | 开启 |
| 表头样式 | bold(粗体) / colored(带背景色) / plain(无样式) | bold |
| 空值显示 | null/undefined 值的显示文本 | 空 |
| 自动列宽 | 根据内容自动调整列宽 | 开启 |
| 预览行数 | 预览表格显示行数上限 | 50 |

---

## ⚠️ Disclaimer

- **"AS IS"**: This software is provided "AS IS", without any express or implied warranty, including but not limited to merchantability, fitness for a particular purpose, and non-infringement.
- **Use at Your Own Risk**: The developer shall not be liable for any direct or indirect losses (including but not limited to data loss, system damage, business interruption) caused by the use of this software. Users must assess and bear all risks.
- **Data Backup**: It is recommended to back up important data before using this software to prevent irreversible loss.
- **Compatibility Risks**: This software may have unknown defects or be incompatible with certain system environments, hardware configurations, or third-party software. The developer does not guarantee normal operation in all environments.
- **Plugin Disclaimer**: Plugins in this application are independent modules. The developer makes no guarantee regarding the behavior, security, or stability of third-party plugins. Users must assess and bear the risks of using third-party plugins.

> Downloading or using this software indicates that you have read and agree to the above disclaimer.
