# YAML 格式化

> 离线 YAML 工作台：格式化（保留注释）、校验与中文错误定位、压缩、四格式互转、扁平化、多文档、JSONPath 查询、规范检查、K8s 离线校验、锚点视图与展开——专为 K8s 清单与 CI 配置场景设计，全程本地处理无网络请求

## 功能介绍

- **格式化 / 校验**：注释与键序保留的往返排版；缩进 2/4、行宽、键排序（码点序，跨机器一致）、单引号风格、序列缩进可配；语法错误按引擎错误码转译为中文说明（缩进不一致 / 引号未闭合 / 流式集合未闭合 / 保留字符 / 无效转义 / 未定义锚点…），英文原文保留对照，一键跳转到错误行并整行高亮。
- **压缩**：流式单行化（每文档一行，去注释、不折行），与格式化互为输出风格开关，偏好持久记忆。
- **多文档**：`---` 分隔的 K8s 多资源文件原生解析——分隔符、文档间注释、`...` 结束符往返保留，块标量内的 `---` 不误切；多文档页逐文档校验、查看、复制，标注起始行与 `kind`。
- **四格式互转**：YAML ⇄ JSON ⇄ TOML ⇄ properties 任意组合，一键换向；`<<` 合并键真正合并进结果；多文档输出 JSON 数组。
- **扁平化**：点号键值表（`spec.containers[0].image`）+ .env 风格导出。
- **查询提取**：JSONPath 子集即时取值——成员访问 / 数组下标与负下标 / 通配符 / `..image` 递归下降，逐行或全部复制。
- **规范检查**：语法之外的 10 条「慢性病」规则——布尔歧义值（yes/on/off）、重复键（不再阻断格式化）、行尾空白、行长、连续空行、文件末尾换行、冒号间距（冒号后缺空格会让整行变成普通文本）、多文档缺 `---` 起始、疑似密钥字段名、八进制前导零丢失；状态栏徽章计数，点击直达，行点击定位。
- **K8s 离线校验**：内置 22 个常用 kind 的 apiVersion 与必填字段清单（Deployment/Service/Ingress/Job…），内网无 schema 也能查出漏字段；未收录 kind 只提示不误报。
- **锚点与合并键**：`&锚点` / `*别名` / `<<` 的定义、引用与引入键一目了然；「展开锚点」一键解引用为普通 YAML（Ctrl+Z 可撤销）。
- **QuickAction**：任意应用选中 YAML 按鼠标中键，面板直接显示校验结论卡（结构统计 / kind / 规范提醒数，或错误行列 + 中文原因 + 上下文）；右键菜单直达格式化 / 转 JSON / 扁平化 / 多文档 / 规范检查；支持多开，连续触发各开新窗互不影响。
- **快捷键**：Ctrl+Enter 格式化 · Ctrl+S 保存文件 · Ctrl+Shift+C 复制结果 · Ctrl+B 折叠侧栏。
- **文件与偏好**：打开 .yaml/.yml/.json 文件、保存结果（原生对话框）；全部选项与布局自动记忆。
- **明暗主题 + 中英双语**：跟随核心主题与语言即时切换。

## 使用说明

1. 打开 My Desktop Tools 进入「YAML 格式化」（或从独立窗口 / QuickAction 打开）；粘贴或打开文件后自动排版。
2. 顶部六页签切换功能：格式化 / 互转 / 扁平化 / 多文档 / 查询 / 检查；左栏输入、右栏结果，分隔条可拖动（双击复位）。
3. 出错时右栏显示中文错误卡，点「跳到第 N 行」直达；状态栏规范徽章点击进检查页，任何一行点击都会定位到输入。
4. 带锚点的清单在检查页可「展开锚点」，提交前把 `&` / `*` / `<<` 全部消解。
5. 全程离线，数据不出本机。

## 技术说明

前端引擎为 `yaml` npm（与 VS Code 官方 YAML 语言服务同源）：多文档走 parseAllDocuments，解析启用 `<<` 合并、重复键不作语法错误；Sidecar（Rust, serde_yaml）只负责 QuickAction 探测与偏好持久化。规范检查概念对齐 yamllint、实现自研（无 GPL 代码）；K8s 校验为离线精简清单（CRD 与低频资源不校验）；TOML 无 null 语义，含空值的文档转 TOML 会提示先清理。输入上限 5MB。

---

<details>
<summary>English</summary>

# YAML Formatter

> Offline YAML workbench: comment-preserving formatting, validation with localized error locating, minify, four-format conversion, flattening, multi-document handling, JSONPath queries, style linting, offline K8s checks, and anchor view/expansion — built for Kubernetes manifests and CI configs; everything runs locally with no network requests.

## Features

- **Format / Validate**: Round-trip formatting that keeps comments and key order; indent 2/4, line width, key sorting (code-point order, machine-independent), single-quote style and sequence indentation are configurable. Syntax errors are translated by engine error code into plain-language messages (inconsistent indentation / unclosed quote / unclosed flow collection / reserved character / bad escape / unresolved anchor…), with the raw engine text kept underneath; one click jumps to and highlights the offending line.
- **Minify**: Flow-style single-lining (one line per document, comments dropped, no wrapping) as a persistent output-style toggle alongside Format.
- **Multi-document**: `---`-separated K8s multi-resource files are parsed natively — separators, inter-document comments and `...` end markers round-trip; `---` inside block scalars is never mis-split. The Documents tab validates, views and copies each document with its start line and `kind`.
- **Four-format conversion**: YAML ⇄ JSON ⇄ TOML ⇄ properties in any combination with one-click direction swap; `<<` merge keys are actually merged into the result; multi-document input converts to a JSON array.
- **Flatten**: Dotted key/value table (`spec.containers[0].image`) plus .env-style export.
- **Query**: JSONPath subset evaluated instantly — member access, array index / negative index, wildcard, `..image` recursive descent; copy a row or everything.
- **Style & sanity checks**: Ten rules beyond syntax — ambiguous booleans (yes/on/off), duplicate keys (no longer block formatting), trailing whitespace, line length, consecutive empty lines, missing newline at EOF, colon spacing (a missing space after a colon turns the whole line into plain text), missing `---` at the start of a multi-document stream, suspicious secret-like key names, octal leading-zero loss; a status-bar badge counts them, click to inspect, click a row to locate.
- **Offline K8s checks**: Built-in apiVersion and required-field lists for 22 common kinds (Deployment/Service/Ingress/Job…) — catch missing fields without network schemas; unknown kinds are only noted, never flagged as errors.
- **Anchors & merge keys**: Definitions, references and merged-in keys of `&anchor` / `*alias` / `<<` at a glance; "Expand anchors" dereferences everything into plain YAML in one click (Ctrl+Z to undo).
- **QuickAction**: Select YAML in any app and press the middle mouse button — the panel shows a verdict card directly (structure stats / kind / lint count, or error line:column with a localized reason and context); the context menu jumps straight to format / to JSON / flatten / documents / inspect. Multiple windows are supported; consecutive triggers each open their own window.
- **Shortcuts**: Ctrl+Enter format · Ctrl+S save file · Ctrl+Shift+C copy result · Ctrl+B toggle sidebar.
- **Files & preferences**: Open .yaml/.yml/.json and save results via native dialogs; all options and layout are remembered.
- **Dark/light theme + Chinese/English UI**: Follows the core theme and language instantly.

## Usage

1. Open My Desktop Tools and go to "YAML Formatter" (or open it from a standalone window / QuickAction); paste or open a file and it formats automatically.
2. Six tabs on top: Format / Convert / Flatten / Documents / Query / Inspect; input on the left, result on the right, draggable splitter (double-click to reset).
3. On errors the right pane shows a localized error card — click "Go to line N" to jump; click the status-bar lint badge to open Inspect, and click any row to locate it in the input.
4. For manifests with anchors, use "Expand anchors" in Inspect to dissolve every `&` / `*` / `<<` before committing.
5. Fully offline — data never leaves this machine.

## Technical notes

The frontend engine is the `yaml` npm package (the same engine behind the official VS Code YAML language server): multi-document parsing via parseAllDocuments, `<<` merge enabled, duplicate keys not treated as syntax errors. The Rust sidecar (serde_yaml) only handles QuickAction probing and preference persistence. Lint rules follow yamllint concepts with an in-house implementation (no GPL code); K8s checks are an offline, trimmed list (CRDs and rare resources are not validated); TOML has no null, so documents containing nulls prompt for cleanup first. Input limit 5MB.

</details>

---

## ⚠️ Disclaimer

- **"AS IS"**: This software is provided "AS IS", without any express or implied warranty, including but not limited to merchantability, fitness for a particular purpose, and non-infringement.
- **Use at Your Own Risk**: The developer shall not be liable for any direct or indirect losses (including but not limited to data loss, system damage, business interruption) caused by the use of this software. Users must assess and bear all risks.
- **Data Backup**: It is recommended to back up important data before using this software to prevent irreversible loss.
- **Compatibility Risks**: This software may have unknown defects or be incompatible with certain system environments, hardware configurations, or third-party software. The developer does not guarantee normal operation in all environments.
- **Plugin Disclaimer**: Plugins in this application are independent modules. The developer makes no guarantee regarding the behavior, security, or stability of third-party plugins. Users must assess and bear the risks of using third-party plugins.

> Downloading or using this software indicates that you have read and agree to the above disclaimer.
