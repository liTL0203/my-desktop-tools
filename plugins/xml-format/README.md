# XML 格式化

> 离线 XML 文本工作台：格式化、压缩、校验定位、结构树、XPath 查询与 JSON 互转

## 功能介绍

- **XML 格式化**：2/4 空格或 Tab 缩进重排；注释、CDATA、声明、处理指令完整保留；纯文本节点保持单行；属性换行策略（同行/逐行/自动）可配。
- **压缩**：一键单行化，去注释与多余空白；文本内容与 CDATA 原样保护。
- **结构校验**：标签配对、引号闭合等多错误一次报全，每处错误定位到行:列，点击直达。
- **结构树**：格式化后自动生成可折叠结构树，点击节点直接跳转到结果行；元素/属性/深度/体积统计一目了然。
- **XPath 查询**：全量 XPath 1.0 语法，预置常用表达式，命中节点点击回定位。
- **XML ⇄ JSON 双向转换**：属性加 `-` 前缀、重复元素合并数组、混合内容用 `#text`；JSON 转 XML 根名可配。
- **实体转义/反转义**：命名实体与数值实体互转。
- **文件支持**：直接打开 / 保存 .xml 文件（原生对话框）。
- **QuickAction**：在任意应用中选中 XML 按中键（或右键菜单），未打开插件也能看到结构统计结论卡；破损 XML 直接给错误定位卡；右键菜单 5 条动作直达（格式化并复制/压缩/转 JSON/校验定位/转义）。
- **明暗主题 + 中英双语**：跟随核心主题与语言即时切换。

## 使用说明

1. 打开 My Desktop Tools，进入「XML 格式化」页面（或从独立窗口 / QuickAction 打开）。
2. 粘贴或打开 XML 文件，点「格式化」；左侧为原始输入，右侧结果/结构树/XPath/转换四页签。
3. 破损文档：状态栏显示错误数，点击即定位到输入中的错误行。
4. 全程离线，数据不出本机。

## 技术说明

引擎为 Rust sidecar（quick-xml + sxd-xpath），前端 CodeMirror 6 语法高亮。校验为 well-formedness（非 XSD 语义校验）；输入上限 2MB。

---

## ⚠️ Disclaimer

- **"AS IS"**: This software is provided "AS IS", without any express or implied warranty, including but not limited to merchantability, fitness for a particular purpose, and non-infringement.
- **Use at Your Own Risk**: The developer shall not be liable for any direct or indirect losses (including but not limited to data loss, system damage, business interruption) caused by the use of this software. Users must assess and bear all risks.
- **Data Backup**: It is recommended to back up important data before using this software to prevent irreversible loss.
- **Compatibility Risks**: This software may have unknown defects or be incompatible with certain system environments, hardware configurations, or third-party software. The developer does not guarantee normal operation in all environments.
- **Plugin Disclaimer**: Plugins in this application are independent modules. The developer makes no guarantee regarding the behavior, security, or stability of third-party plugins. Users must assess and bear the risks of using third-party plugins.

> Downloading or using this software indicates that you have read and agree to the above disclaimer.
