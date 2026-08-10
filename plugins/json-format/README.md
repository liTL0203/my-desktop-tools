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

## ⚠️ Disclaimer

- **"AS IS"**: This software is provided "AS IS", without any express or implied warranty, including but not limited to merchantability, fitness for a particular purpose, and non-infringement.
- **Use at Your Own Risk**: The developer shall not be liable for any direct or indirect losses (including but not limited to data loss, system damage, business interruption) caused by the use of this software. Users must assess and bear all risks.
- **Data Backup**: It is recommended to back up important data before using this software to prevent irreversible loss.
- **Compatibility Risks**: This software may have unknown defects or be incompatible with certain system environments, hardware configurations, or third-party software. The developer does not guarantee normal operation in all environments.
- **Plugin Disclaimer**: Plugins in this application are independent modules. The developer makes no guarantee regarding the behavior, security, or stability of third-party plugins. Users must assess and bear the risks of using third-party plugins.

> Downloading or using this software indicates that you have read and agree to the above disclaimer.
