# JSON 格式化

JSON 解析、格式化、压缩、JS 处理与多维可视化工具。

## 功能

- **格式化 / 压缩**：一键美化或压缩 JSON，支持 2/4 空格缩进
- **JS 处理**：编写自定义 JS 脚本对数据进行筛选、映射、转换，实时预览结果
- **多维可视化**：自动判断并切换表格、图片、树形、文本四种视图
  - 表格：大数据虚拟滚动、列排序、悬停查看完整值
  - 图片：base64 / URL 图片网格展示，点击放大
  - 树形：惰性展开，深层嵌套不卡顿
  - 文本：语法高亮 + 行号 + 分页加载
- **JS 片段库**：保存常用处理逻辑，支持分组、排序、一键插入与快捷运行
- **本地文件**：打开 / 保存 JSON 文件（原生对话框）
- **大文件友好**：解析与处理在独立 Web Worker 中执行，界面永不卡死

## 使用说明

1. **输入数据**：在左侧「JSON 输入」面板粘贴 JSON，或点击工具栏「打开文件」加载本地文件
2. **格式化**：点击工具栏「格式化」将结果回填输入区；「压缩」输出单行 JSON
3. **JS 处理**：切换到「JS 处理」标签，编写函数体脚本（参数 `data` 为当前数据），点击「运行」；脚本需 `return` 可 JSON 序列化的结果
   - 语法错误 / 运行时错误会在结果区顶部显示类型、消息与行号
   - 死循环脚本 5 秒自动终止，不影响插件使用
4. **视图切换**：结果区顶部 Tab 可手动切换表格 / 图片 / 树形 / 文本，「自动」为智能判断
5. **片段管理**：点击工具栏「片段」，可新建分组与片段；「插入」将代码插入脚本编辑器，「运行」立即执行
6. **布局**：拖拽中间分隔条调整输入面板宽度（20%~60%），双击折叠；工具栏可全屏预览

## 注意事项

- 输入上限 50MB，超出将被拒绝
- JS 脚本在隔离的 Worker 中执行，无界面与文件访问能力；脚本由用户本人编写，等价于浏览器控制台执行
- 片段与界面偏好存储在 `%APPDATA%\my-desktop-tools\plugins\json-format\`，卸载插件不残留
- 支持内嵌（inapp）与独立窗口（desktop / popup）模式

## 版本信息

**v0.1.0**（首个版本）

- 基础格式化 / 压缩 / 校验
- JS 处理（Worker 隔离 + 超时保护）
- 四视图可视化（表格 / 图片 / 树形 / 文本）
- JS 片段库（分组 / 排序 / 持久化）
- 本地文件打开 / 保存

---

<details>
<summary>English</summary>

# JSON Formatter

> JSON parsing, formatting, minification, custom JS processing and multi-view visualization tool.

## Features

- **Formatting / Minification**: Beautify or minify JSON with one click; 2/4 space indentation supported
- **Custom JS Processing**: Write custom JS scripts to filter, map and transform data with real-time result preview
- **Multi-view Visualization**: Automatically detects and switches among table, image, tree and text views
  - Table: virtual scrolling for large data, column sorting, hover to view full values
  - Image: grid display of base64 / URL images, click to zoom
  - Tree: lazy expansion, deep nesting without lag
  - Text: syntax highlighting + line numbers + paginated loading
- **JS Snippet Library**: Save frequently used processing logic; supports grouping, sorting, one-click insertion and quick run
- **Local Files**: Open / save JSON files (native dialogs)
- **Large-file Friendly**: Parsing and processing run in a dedicated Web Worker, so the UI never freezes

## Usage

1. **Input Data**: Paste JSON into the "JSON Input" panel on the left, or click "Open File" on the toolbar to load a local file
2. **Formatting**: Click "Format" on the toolbar to write the result back into the input area; "Minify" outputs single-line JSON
3. **Custom JS Processing**: Switch to the "JS Processing" tab, write a function body script (the parameter `data` is the current data), then click "Run"; the script must `return` a JSON-serializable result
   - Syntax / runtime errors show type, message and line number at the top of the result area
   - Infinite-loop scripts are terminated automatically after 5 seconds without affecting the plugin
4. **View Switching**: Tabs at the top of the result area allow manual switching among table / image / tree / text; "Auto" uses smart detection
5. **Snippet Management**: Click "Snippets" on the toolbar to create groups and snippets; "Insert" puts the code into the script editor, "Run" executes it immediately
6. **Layout**: Drag the middle divider to adjust the input panel width (20%~60%), double-click to collapse; the toolbar offers fullscreen preview

## Notes

- Input limit is 50MB; larger inputs are rejected
- JS scripts run in an isolated Worker with no UI or file access capability; scripts are written by the users themselves, equivalent to executing in the browser console
- Snippets and UI preferences are stored in `%APPDATA%\my-desktop-tools\plugins\json-format\`; nothing is left behind after uninstalling the plugin
- Supports embedded (inapp) and standalone window (desktop / popup) modes

## Version History

**v0.1.0** (first release)

- Basic formatting / minification / validation
- Custom JS processing (Worker isolation + timeout protection)
- Four-view visualization (table / image / tree / text)
- JS snippet library (grouping / sorting / persistence)
- Local file open / save

</details>

---

## ⚠️ Disclaimer

- **"AS IS"**: This software is provided "AS IS", without any express or implied warranty, including but not limited to merchantability, fitness for a particular purpose, and non-infringement.
- **Use at Your Own Risk**: The developer shall not be liable for any direct or indirect losses (including but not limited to data loss, system damage, business interruption) caused by the use of this software. Users must assess and bear all risks.
- **Data Backup**: It is recommended to back up important data before using this software to prevent irreversible loss.
- **Compatibility Risks**: This software may have unknown defects or be incompatible with certain system environments, hardware configurations, or third-party software. The developer does not guarantee normal operation in all environments.
- **Plugin Disclaimer**: Plugins in this application are independent modules. The developer makes no guarantee regarding the behavior, security, or stability of third-party plugins. Users must assess and bear the risks of using third-party plugins.

> Downloading or using this software indicates that you have read and agree to the above disclaimer.
