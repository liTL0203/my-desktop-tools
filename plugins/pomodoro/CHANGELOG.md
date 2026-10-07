# v3.2.0 更新说明 (2026-10-08)

## 新增（竞品对标增量：节奏与洞察包 + 情感与声音包）

- **自由专注**：正计时模式（无固定时长），环呈旋转弧呼吸态，手动完成按实际时长计入；暂停/恢复/停止语义完整
- **目标双口径**：每日目标支持按分钟或按番茄数，今日卡/连续天数判定/统计瓦片全链路联动
- **预计完成时间**：任务视图按剩余预估番茄 × 当前模式时长推算"预计 HH:MM 完成今日任务"
- **打断归因**：分心记事可打标签（被打断/杂念/想休息/想刷手机），统计新增打断原因分布卡
- **像素番茄花园**：近 14 天番茄收获以像素植物呈现，品种按累计番茄数解锁（芽→苗→丛→树→花树→金树）；数据派生自热力图，零新增存储
- **音景扩展与混音**：新增海浪（LFO 浪涌）与微风（带通漂移）配方；主/辅双通道独立音量混音；休息时可自动切换指定音景
- **周报卡**：统计视图新增本周 vs 上周环比
- **分享卡片**：canvas 生成今日成绩卡（含近 7 天条形），经文件保存桥落盘 PNG
- **任务备注**：单条备注，任务行展示与编辑
- **热力图双数据**：悬停显示当日分钟数与番茄数
- **预备启动**（默认关）：开始专注前 3-2-1 预备动画，Esc 可取消
- **音景试听动效**：激活胶囊带波形条动画

## 修复

- 统计瓦片目标行在番茄口径下仍显示分钟目标的问题

---

# v3.0.0 更新说明 (2026-09-26)

## 重设计（存储格式换代，旧数据自动备份为 .v2.bak，不迁移）

### 新增
- 节奏预设：经典 25+5 / 深度 50+10 / 自定义，胶囊切换 + 快捷键 1/2/3
- 任务绑定：任务清单（预估番茄数/进度点/投入分钟）+「专注此任务」一键启动
- 休息引导：20-20-20 护眼倒数（短休）与 4-4-6 呼吸动画（长休）
- 分心记事本：专注中随手记录，休息时逐条勾掉
- 专注洞察：连续天数/最佳纪录、12 周热力图、24h 时段分布（黄金时段）、任务投入排行
- 合成音景：雨声/壁炉/咖啡馆（Web Audio 实时合成，无音频文件），可专注自动播放
- 严格模式：专注中禁暂停（仅可放弃且不计入统计）
- 数据导出：CSV（UTF-8 BOM）/ JSON，保存路径走核心文件桥
- 兜底提醒：窗口关闭时 Sidecar 播放 Windows 系统提示音（前端 ack 去重）
- 页面内完成横幅 + 最后 10 秒滴答 + 键盘快捷键（Space/S/E/Esc）

### 变更
- 计时改墙钟基准（phase_end_unix）：系统睡眠唤醒后进度与真实时间一致
- 完成语义四分：natural / early（≥1 分钟计入）/ skipped / abandoned，统计口径不再失真
- 自动衔接拆为双开关：专注完成进休息（默认开）、休息结束回专注（默认关）
- 会话记录按月分片（sessions-YYYY-MM.jsonl），统计只读覆盖月份
- 三视图工作台 UI（专注/任务/统计）+ 设置弹层；深浅双主题与中英文完整适配
- metadata 宣传口径与实现对齐（废弃"番茄钟 Pro"叫法）

### 修复
- idle 态调用 skip 会凭空启动休息倒计时（增加状态校验）
- 跨日统计的 UTC/本地时区混用偏差（统一本地日期边界）
- 提前完成不记录导致统计失真

---

# v2.4.0 更新说明 (2026-09-25)

## 新增
- Sidecar 依赖升级与工程同步（随核心 1.2.17 生态）

---

# v2.3.2 更新说明 (2026-09-23)

## 优化
- 维护性同步：随核心 1.2.14 发布周期对齐（构建与工程配置），无功能变化

---

# v2.3.1 更新说明 (2026-09-16)

## 修复
- 修复市场安装的插件在侧边栏/气泡显示占位图标的问题——ZIP 现已包含插件图标文件
- 构建配置适配 pnpm v12（工程内部，不影响使用）

---

# v2.3.0 更新说明 (2026-09-16)

## 优化
- 稳定性细节维护，随核心 1.2 生态同步

---

# v2.2.2 更新说明 (2026-09-16)

## 优化
- 内部代码质量加固（除零防护、日志过滤等稳定性细节）

---

# v2.1.2 Release Notes (2026-08-18)

## Maintenance
- Version sync release: no functional changes; explicitly marked as public plugin (private: false)

<details>
<summary>中文说明</summary>

# v2.1.2 更新说明 (2026-08-18)

## 维护
- 版本同步发布：无功能性变更；显式标记为公开插件（private: false）

</details>

---

# v2.1.0 Release Notes (2026-07-14)

## New Features
- **Internationalization**: Plugin name now supports automatic Chinese/English switching, following the core application language setting

<details>
<summary>中文说明</summary>

# v2.1.0 更新说明 (2026-07-14)

## 新增功能
- **国际化支持**: 插件名称支持中英文自动切换，跟随核心程序语言设置

</details>

---

# v2.0.0 Release Notes (2026-04-01)

## New Features
- Standalone plugin version
- Light/dark theme support
- Hotkey support
- Auto short-break/long-break switching
- Local statistics persistence

## Improvements
- Refactored to standalone plugin architecture
- Optimized timer accuracy
- Improved UI interaction experience

<details>
<summary>中文说明</summary>

# v2.0.0 更新说明 (2026-04-01)

## 新增
- 独立插件版本
- 支持亮色/暗色主题
- 支持快捷键操作
- 自动短休息/长休息切换
- 统计记录本地持久化

## 优化
- 重构为独立插件架构
- 优化计时器精度
- 改进 UI 交互体验

</details>

---

# v1.0.0 Release Notes (2026-03-01)

## New Features
- Initial release
- 25-minute focus mode
- 5-minute short break
- 15-minute long break
- Auto cycle switching

<details>
<summary>中文说明</summary>

# v1.0.0 更新说明 (2026-03-01)

## 新增
- 初始版本
- 25 分钟专注模式
- 5 分钟短休息
- 15 分钟长休息
- 自动循环切换

</details>
