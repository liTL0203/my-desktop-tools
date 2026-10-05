# 截图助手

> 截图、标注、提取文字与翻译：热键唤起，框选即截，识别翻译一步到位。

## 功能介绍

- **区域截图**：按 `Ctrl + Alt + A`（可在打开的面板中直接点「开始截图」），画面冻结后拖拽框选；**悬停自动识别整窗，点击即选**；8 个控制点微调、方向键挪动选区（按住 Shift 步进×10）、3 倍放大镜显示像素坐标与颜色值；支持**延时截图**（立即/1-5 秒）。
- **标注**：矩形 / 椭圆 / 箭头 / 画笔 / **高亮笔** / 马赛克 / 文字 / **序号标签①②③**，8 色色板可调，**绘制中滚轮调节粗细**、工具栏右键快速换色，撤销（Ctrl+Z）与重做（Ctrl+Y），双击选区重复上次动作。
- **贴图钉屏**：截完点「贴图」钉在原位，随时对照参考；悬停工具栏：缩放（25% 档）/ 不透明度 / 拖拽移动 / 关闭，最多 6 张常驻。
- **提取文字（OCR）**：Windows 系统内置引擎，完全离线、图片不出本机；小字自动放大增强识别；结果按块勾选、智能合并、行内悬停「译此行」、一键复制全部。
- **翻译与问答**：复用主程序「AI 服务」已配置的模型（零配置）；对照 / 贴回原图两种形态，术语感知提升专业文本质量；还可一键**问 AI**（解释内容 / 解释报错 / 总结要点 / 自由提问）。
- **历史记录**：复制/保存/贴图自动归档，**按截图内容搜索**（识别文字全文索引），预览 / 重新复制 / 删除 / 清空，保留策略可设。
- **导出**：回车即复制到剪贴板（直接粘贴进聊天）；另存 PNG（无损）/ JPG（质量可调）。

## 使用说明

1. 打开 My Desktop Tools，在插件列表启用「截图助手」（默认随主程序自启，保证热键随时可用）。
2. 按 `Ctrl + Alt + A` **直接进入截图**——屏幕冻结后拖拽框选即可，全程不出现插件窗口（也可从插件面板点「开始截图」）。
3. 拖拽框选区域 → 需要标注时从工具栏选工具，在选区内直接绘制（鼠标会切换为对应功能的指针样式）。
4. 点「提取文字」识别选区文字；点「翻译」对识别结果翻译；或直接回车完成复制。
5. `Esc` 随时取消并退出（右上角也有常驻「取消」按钮）。

## 注意事项

- 热键若与其他软件（如微信 Alt+A、QQ Ctrl+Alt+A）冲突，以先注册者生效；可在对应软件中修改热键让位。
- **贴图钉屏与热键直达需配套新版主程序**（覆盖窗自由定位 / 热键分发能力）；旧版主程序上其余功能不受影响。
- 提取文字需要系统已安装对应语言的 OCR 语言包（中文系统一般已内置；若缺失，按面板提示到「设置 → 时间和语言 → 语言」添加并勾选 OCR）。
- 翻译与问 AI 依赖主程序 AI 服务中已配置可用的模型；未配置时面板给出提示，不影响截图/标注/复制等本地功能。
- v1 冻结画面与选区在主显示器；多显示器全屏支持将在后续版本提供。
- 截图与识别全程本地完成；翻译仅将提取后的文本经主程序 AI 网关发送。

## 版本信息

| 版本 | 日期 | 说明 |
|------|------|------|
| 1.1.14 | 2026-10-05 | 截图完成后历史记录即时可见（归档广播 + 面板聚焦/可见自动静默刷新） |
| 1.1.13 | 2026-10-05 | 修复中文识别结果逐字带空格的问题（显示与内容搜索一并修正） |
| 1.1.12 | 2026-10-05 | 历史卡片长文件名改为单行中部省略，悬停可看全名 |
| 1.1.11 | 2026-10-05 | 主面板标题层级重做（分组眉题 + 卡片式设置分组） |
| 1.1.10 | 2026-10-05 | 历史记录视觉重做（徽标沉入缩略图渐变、悬停操作、卡片网格） |
| 1.1.1 - 1.1.9 | 2026-10-05 ~ 10-07 | 真机迭代修复批：窗口吸附与圈选手势区分、覆盖层定位、任务栏可截、文字标注输入/单击重编辑焦点族修复、移除「开窗即截」 |
| 1.1.0 | 2026-10-06 | 贴图钉屏、历史+OCR 搜索、窗口吸附、序号/高亮标注、延时截图、截图问答、微交互包 |
| 0.1.0 | 2026-09-25 | 初始版本：区域截图、标注、OCR 提取、翻译、复制/保存 |

---

<details>
<summary>English</summary>

# Screenshot Assistant

> Capture, annotate, extract text and translate — one hotkey, one drag, done.

## Features

- **Region capture**: press `Ctrl + Alt + A` (or click "Start capture" in the panel). After the screen freezes, drag to select; hover snaps to a whole window, click to select it; fine-tune with 8 handles or arrow keys (Shift = ×10 steps); a 3x magnifier shows pixel coordinates and color values; delayed capture supported (0-5 s).
- **Annotations**: rectangle / ellipse / arrow / pen / highlighter / mosaic / text / numbered tags, with an 8-color palette, wheel-to-resize strokes, right-click to recolor, undo (Ctrl+Z) and redo (Ctrl+Y); double-click repeats the last action.
- **Pin to screen**: pin the capture in place for reference; hover the toolbar for zoom (25% steps), opacity, drag and close; up to 6 pins stay on screen.
- **Extract text (OCR)**: powered by the built-in Windows OCR engine — fully offline, no image ever leaves your device. Small text is auto-upscaled for better accuracy; results are selectable blocks with smart merging and one-click copy.
- **Translation & Ask AI**: reuses the models already configured in the host app's AI service — zero extra setup. Side-by-side and in-place overlay modes; one-click questions about the capture (explain / explain error / summarize / free-form).
- **History**: captures are archived automatically; search by content (OCR full-text index); preview, re-copy, delete or clear; retention policy configurable.
- **Export**: Enter copies the image to the clipboard, ready to paste into chat; save as lossless PNG or adjustable-quality JPG.

## Usage

1. Open My Desktop Tools and enable "Screenshot Assistant" (it auto-starts with the host so the hotkey is always ready).
2. Press `Ctrl + Alt + A` to jump straight into capture — no plugin window appears; drag to select on the frozen screen (you can also click "Start capture" in the panel).
3. Drag to select a region; pick a tool from the toolbar to annotate inside the selection.
4. Click "Extract text" to OCR the selection, "Translate" to translate the results, or just press Enter to copy.
5. `Esc` cancels at any time (a cancel button is always available in the top-right corner).

## Notes

- If the hotkey conflicts with other software (e.g. WeChat's Alt+A), whichever registers first wins; adjust the other app's hotkey if needed.
- Text extraction requires the corresponding Windows OCR language pack (usually preinstalled on Chinese systems; otherwise add it under Settings → Time & language → Language with OCR checked).
- Translation depends on a configured model in the host AI service; without one, the translation panel shows a readable hint while all local features keep working.
- v1 freezes and selects on the primary display only; full multi-monitor support arrives in a later version.
- Capture and recognition are fully local; translation only sends the extracted text through the host AI gateway.

## Version History

| Version | Date | Notes |
|---------|------|-------|
| 1.1.14 | 2026-10-05 | History refreshes instantly after each capture (archive broadcast + focus/visibility refresh) |
| 1.1.13 | 2026-10-05 | Fixed per-character spaces in Chinese OCR results (display and content search) |
| 1.1.12 | 2026-10-05 | Long filenames in history cards shown as single-line middle ellipsis, full name on hover |
| 1.1.11 | 2026-10-05 | Main panel title hierarchy redesign (section eyebrows + card groups) |
| 1.1.10 | 2026-10-05 | History visual redesign (badges over thumbnail gradient, hover actions, card grid) |
| 1.1.1 - 1.1.9 | 2026-10-05 ~ 10-07 | Real-machine iteration fixes: window snap vs free selection, overlay positioning, taskbar capture, text tool focus fixes, removed open-to-capture |
| 1.1.0 | 2026-10-06 | Pin to screen, history + OCR full-text search, window snap, numbered/highlighter annotations, delayed capture, ask AI, micro-interactions |
| 0.1.0 | 2026-09-25 | Initial release: region capture, annotations, OCR, translation, copy/save |

</details>

---

## ⚠️ Disclaimer

- **"AS IS"**: This software is provided "AS IS", without any express or implied warranty, including but not limited to merchantability, fitness for a particular purpose, and non-infringement.
- **Use at Your Own Risk**: The developer shall not be liable for any direct or indirect losses (including but not limited to data loss, system damage, business interruption) caused by the use of this software. Users must assess and bear all risks.
- **Data Backup**: It is recommended to back up important data before using this software to prevent irreversible loss.
- **Compatibility Risks**: This software may have unknown defects or be incompatible with certain system environments, hardware configurations, or third-party software. The developer does not guarantee normal operation in all environments.
- **Plugin Disclaimer**: Plugins in this application are independent modules. The developer makes no guarantee regarding the behavior, security, or stability of third-party plugins. Users must assess and bear the risks of using third-party plugins.

> Downloading or using this software indicates that you have read and agree to the above disclaimer.
