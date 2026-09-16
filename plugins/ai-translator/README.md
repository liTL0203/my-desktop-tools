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

## ⚠️ Disclaimer

- **"AS IS"**: This software is provided "AS IS", without any express or implied warranty, including but not limited to merchantability, fitness for a particular purpose, and non-infringement.
- **Use at Your Own Risk**: The developer shall not be liable for any direct or indirect losses (including but not limited to data loss, system damage, business interruption) caused by the use of this software. Users must assess and bear all risks.
- **Data Backup**: It is recommended to back up important data before using this software to prevent irreversible loss.
- **Compatibility Risks**: This software may have unknown defects or be incompatible with certain system environments, hardware configurations, or third-party software. The developer does not guarantee normal operation in all environments.
- **Plugin Disclaimer**: Plugins in this application are independent modules. The developer makes no guarantee regarding the behavior, security, or stability of third-party plugins. Users must assess and bear the risks of using third-party plugins.

> Downloading or using this software indicates that you have read and agree to the above disclaimer.
