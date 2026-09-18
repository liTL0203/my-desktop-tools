# AI 翻译

选中文字后一键 AI 翻译：自动识别源语言，多目标语言同屏对照，历史可搜索收藏。

## 功能介绍

- **多目标同屏**：弹窗中可同时选择最多 4 门目标语言，每门语言一张结果卡，独立复制、单独重译
- **一键翻译**：在任意应用中选中文字，通过鼠标中键触发快捷操作面板，选择「AI 翻译」即可
- **自动识别源语言**：无需手动选择源语言，界面实时显示识别结果
- **语言库扩展**：内置 12 种语言，快捷语言可自定义（最多 6 门显示在弹窗顶部）
- **翻译历史**：搜索、收藏置顶、单条删除，容量可在设置中调整（20/50/100/200 条）
- **自定义模板**：除通用/技术/口语三种预设外，可用 {lang} 占位符编写自己的翻译风格
- **AI 驱动**：调用核心程序配置的 AI 服务（DeepSeek、OpenAI、Claude、Ollama 等），无需自建模型
- **翻译模型可选**：默认跟随系统默认模型，也可在设置中指定「AI 服务 → 模型」字典中的任意翻译可用模型；切换系统默认模型后下一次翻译立即生效

## 使用说明

1. 在核心程序「AI 服务 → 模型」页面添加提供方与模型，并设置默认模型
2. 在任意应用中选中需要翻译的文字
3. 按下鼠标中键（或自定义快捷键）唤起快捷操作面板，选择「AI 翻译」
4. 翻译结果自动展示在弹窗中；点击顶部语言胶囊可增删目标语言（每门语言独立成卡）
5. 底栏支持全部重译与复制全部；主窗口内可使用 Ctrl+Enter 快捷翻译、查看与搜索历史

## 注意事项

- 使用前需在核心程序「AI 服务 → 模型」中配置提供方、密钥与默认模型
- 翻译模型已升级为系统统一管理：提供方与密钥在「AI 服务 → 模型」字典中维护，插件设置页仅选择使用哪个模型
- 翻译功能依赖网络连接（本地 Ollama 除外）
- 多目标翻译会按语言数产生多次 AI 请求，首次开启多选时会收到成本提示

## 版本信息

- 版本：2.1.0
- 作者：My Desktop Tools
- 依赖核心版本：v0.36.2+（模型选择功能需更高版本，跟随默认模式不受限）

---

<details>
<summary>English</summary>

# AI Translator

> One-click AI selection translation: automatic source language detection, multi-target side-by-side comparison, searchable and favorite-capable history.

## Features

- **Multi-target Side by Side**: Select up to 4 target languages at once in the popup; each language gets its own result card with independent copy and individual re-translation
- **One-click Translation**: Select text in any application, trigger the quick action panel with the middle mouse button, and choose "AI Translator"
- **Automatic Source Language Detection**: No need to pick the source language manually; the UI shows the detected result in real time
- **Extensible Language Library**: 12 built-in languages; quick languages are customizable (up to 6 shown at the top of the popup)
- **Translation History**: Search, pin favorites, delete individual entries; capacity adjustable in settings (20/50/100/200 entries)
- **Custom Templates**: Besides the general/technical/colloquial presets, write your own translation style with the {lang} placeholder
- **Multi-engine AI**: Calls the AI services configured in the core app (DeepSeek, OpenAI, Claude, Ollama, etc.); no need to host your own model
- **Selectable Translation Model**: Follows the system default model by default, or pick any translation-capable model from the "AI Service → Models" dictionary in settings; switching the system default model takes effect on the very next translation

## Usage

1. Add providers and models on the core app's "AI Service → Models" page and set a default model
2. Select the text to translate in any application
3. Press the middle mouse button (or a custom hotkey) to bring up the quick action panel and choose "AI Translator"
4. Translation results appear automatically in the popup; click the language capsules at the top to add or remove target languages (each language gets its own card)
5. The bottom bar supports re-translating all and copying all; the main window offers Ctrl+Enter quick translation plus history viewing and search

## Notes

- Before use, configure providers, keys and the default model in the core app's "AI Service → Models"
- Translation models are now managed centrally by the system: providers and keys are maintained in the "AI Service → Models" dictionary, and the plugin settings page only selects which model to use
- Translation requires a network connection (except local Ollama)
- Multi-target translation produces one AI request per language; a cost notice appears when multi-select is first enabled

## Version History

- Version: 2.1.0
- Author: My Desktop Tools
- Required core version: v0.36.2+ (the model selection feature requires a newer version; the follow-default mode is not restricted)

</details>

---

## ⚠️ Disclaimer

- **"AS IS"**: This software is provided "AS IS", without any express or implied warranty, including but not limited to merchantability, fitness for a particular purpose, and non-infringement.
- **Use at Your Own Risk**: The developer shall not be liable for any direct or indirect losses (including but not limited to data loss, system damage, business interruption) caused by the use of this software. Users must assess and bear all risks.
- **Data Backup**: It is recommended to back up important data before using this software to prevent irreversible loss.
- **Compatibility Risks**: This software may have unknown defects or be incompatible with certain system environments, hardware configurations, or third-party software. The developer does not guarantee normal operation in all environments.
- **Plugin Disclaimer**: Plugins in this application are independent modules. The developer makes no guarantee regarding the behavior, security, or stability of third-party plugins. Users must assess and bear the risks of using third-party plugins.

> Downloading or using this software indicates that you have read and agree to the above disclaimer.
