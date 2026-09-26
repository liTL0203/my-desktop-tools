# 截图助手

> 截图、标注、提取文字与翻译：热键唤起，框选即截，识别翻译一步到位。

## 功能介绍

- **区域截图**：按 `Ctrl + Alt + A`（可在打开的面板中直接点「开始截图」），画面冻结后拖拽框选；8 个控制点微调、方向键挪动选区（按住 Shift 步进×10）、框选时有 3 倍放大镜辅助对齐，并显示像素坐标与颜色值。
- **标注**：矩形 / 椭圆 / 箭头 / 画笔 / 马赛克 / 文字六种工具，8 色色板与三档粗细可调，支持撤销（Ctrl+Z）与重做（Ctrl+Y）。
- **提取文字（OCR）**：使用 Windows 系统内置 OCR 引擎，完全离线、图片不出本机；识别结果按块列出，可勾选、智能合并成段落，一键复制全部。
- **翻译**：复用主程序「AI 服务」中已配置的模型，无需在本插件内再次配置密钥；支持「对照」与「贴回原图」两种形态，可复制译文或双语对照。
- **导出**：回车或点「完成」即复制图片到剪贴板（可在聊天窗口直接粘贴）；也可另存为 PNG（无损）或 JPG（质量可调）。

## 使用说明

1. 打开 My Desktop Tools，在插件列表启用「截图助手」（默认随主程序自启，保证热键随时可用）。
2. 按 `Ctrl + Alt + A` **直接进入截图**——屏幕冻结后拖拽框选即可，全程不出现插件窗口（也可从插件面板点「开始截图」）。
3. 拖拽框选区域 → 需要标注时从工具栏选工具，在选区内直接绘制（鼠标会切换为对应功能的指针样式）。
4. 点「提取文字」识别选区文字；点「翻译」对识别结果翻译；或直接回车完成复制。
5. `Esc` 随时取消并退出（右上角也有常驻「取消」按钮）。

## 注意事项

- 热键若与其他软件（如微信 Alt+A、QQ Ctrl+Alt+A）冲突，以先注册者生效；可在对应软件中修改热键让位。
- 提取文字需要系统已安装对应语言的 OCR 语言包（中文系统一般已内置；若缺失，按面板提示到「设置 → 时间和语言 → 语言」添加并勾选 OCR）。
- 翻译功能依赖主程序 AI 服务中已配置可用的模型；未配置时翻译面板会给出提示，不影响截图/标注/复制等本地功能。
- v1 冻结画面与选区在主显示器；多显示器全屏支持将在后续版本提供。
- 截图与识别全程本地完成；翻译仅将提取后的文本经主程序 AI 网关发送。

## 版本信息

| 版本 | 日期 | 说明 |
|------|------|------|
| 0.1.0 | 2026-09-25 | 初始版本：区域截图、标注、OCR 提取、翻译、复制/保存 |

---

<details>
<summary>English</summary>

# Screenshot Assistant

> Capture, annotate, extract text and translate — one hotkey, one drag, done.

## Features

- **Region capture**: press `Ctrl + Alt + A` (or click "Start capture" in the panel). After the screen freezes, drag to select; fine-tune with 8 handles or arrow keys (Shift = ×10 steps); a 3x magnifier shows pixel coordinates and color values while dragging.
- **Annotations**: rectangle / ellipse / arrow / pen / mosaic / text, with an 8-color palette and three stroke widths; undo (Ctrl+Z) and redo (Ctrl+Y) supported.
- **Extract text (OCR)**: powered by the built-in Windows OCR engine — fully offline, no image ever leaves your device. Results are listed block by block, selectable, mergeable into paragraphs, and copyable in one click.
- **Translation**: reuses the models already configured in the host app's AI service — zero extra setup. Side-by-side and in-place overlay modes; copy translated text or both languages.
- **Export**: Enter (or the check button) copies the image to the clipboard, ready to paste into chat; save as lossless PNG or adjustable-quality JPG is also available.

## Usage

1. Open My Desktop Tools and enable "Screenshot Assistant" (it auto-starts with the host so the hotkey is always ready).
2. Press `Ctrl + Alt + A`; the panel automatically starts capturing (or click "Start capture").
3. Drag to select a region; pick a tool from the toolbar to annotate inside the selection.
4. Click "Extract text" to OCR the selection, "Translate" to translate the results, or just press Enter to copy.
5. `Esc` cancels at any time.

## Notes

- If the hotkey conflicts with other software (e.g. WeChat's Alt+A), whichever registers first wins; adjust the other app's hotkey if needed.
- Text extraction requires the corresponding Windows OCR language pack (usually preinstalled on Chinese systems; otherwise add it under Settings → Time & language → Language with OCR checked).
- Translation depends on a configured model in the host AI service; without one, the translation panel shows a readable hint while all local features keep working.
- v1 freezes and selects on the primary display only; full multi-monitor support arrives in a later version.
- Capture and recognition are fully local; translation only sends the extracted text through the host AI gateway.

## Version History

| Version | Date | Notes |
|---------|------|-------|
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
