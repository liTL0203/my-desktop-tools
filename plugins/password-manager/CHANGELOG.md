# v2.2.1 更新说明 (2026-09-16)

## 新增
- 锁屏界面风险确认验证——初始化与完成流程中未确认风险时会给出醒目提示，防误操作

## 修复
- 插件状态显示一致性修复（随核心 1.2.1 联动）

---

# v2.2.0 更新说明 (2026-09-16)

## 优化
- 随核心覆盖窗口能力同步适配

---

# v2.1.0 更新说明 (2026-09-16)

## 新增
- 全新 v2 密码库：数据目录独立于程序安装位置，升级与卸载不再影响数据安全
- 功能说明气泡体系，新手引导更完善

## 修复
- 引导弹窗关闭问题修复

## 优化
- 代码质量加固

---

# v2.0.0 Release Notes (2026-09-07)

> **Complete rewrite.** The vault format, sidecar and frontend are rebuilt from the ground up. v1 data is not compatible (legacy vault files are quarantined, never read or deleted). This plugin never shipped to real users, so no migration is provided.

## New Features

- **Zero-Knowledge Vault (rebuilt)**: Argon2id key derivation + field-level AES-256-GCM with AAD binding (anti field-swap hardening); brute-force throttling and idle auto-lock
- **Setup Wizard**: live strength meter + one-time 160-bit recovery key (skippable with explicit risk acknowledgment)
- **Custom Fields**: per-entry key-value fields with secret masking and guarded copy
- **Search**: instant filtering incl. Chinese pinyin initials
- **Windows Hello Quick Unlock**: DPAPI-bound key cache; lock-screen primary button; synced on master-password change
- **TOTP (RFC 6238)**: paste a Base32 secret or otpauth:// link; live 6-digit code with 30s countdown ring inline in every list; one-click copy with auto-clear
- **Health Check 2.0 (ECharts)**: score gauge + risk bar chart; weak / reused / stale / http / 2FA-candidate findings with direct fix actions
- **Auto Snapshots**: daily-on-first-unlock + forced before dangerous operations; rolling 10; one-click restore (file-level swap with pre-restore safety snapshot)
- **Trash**: 30-day recycle bin with restore
- **Auto-Type**: fill username→TAB→password→ENTER into the previous external window (Z-order walk-back, focus guard, IME guard, elevated-window detection); multi-account candidate panel
- **Encrypted Backup (.mdvault)**: independent backup password, merge / overwrite restore; TOTP secrets included in backups
- **Forgot-Password Wizard**: self-checked recovery paths (Hello / recovery key / rebuild from backup / archive-and-rebuild); recovery-key sessions gate sensitive ops until the master password is reset
- **QuickAction Integration**: select credentials text → save into the vault with auto-parsed prefill
- **Popup Quick-Retrieve Mode**: single-column flow under 480px — search-focused, keyboard-driven, inline copy / TOTP / Auto-Type

## Removed (by design)

- Nested folder tree (now 1-level folders + tags), window-match keywords, custom auto-type sequences, domain isolation, auto-popping guides — the v1 concepts that buried the main flow
- v1 data compatibility (see note above)

<details>
<summary>中文说明</summary>

# v2.0.0 更新说明 (2026-09-07)

> **全新重写。** 保险库格式、Sidecar 与前端全部从零重建。不兼容 v1 数据（旧库文件自动隔离改名，不读取不删除）。本插件从未有真实用户，故不提供迁移。

## 新增功能

- **零知识保险库（重建）**：Argon2id 派生 + 字段级 AES-256-GCM（AAD 绑定防字段调换）；防暴力延迟与闲置自动锁定
- **创建向导**：实时强度评估 + 一次性 160-bit 恢复密钥（可跳过需确认风险）
- **自定义字段**：条目级键值字段，密码型遮蔽显示、复制走守护通道
- **搜索**：即时过滤，支持中文拼音首字母
- **Windows Hello 快速解锁**：DPAPI 绑定密钥缓存；锁屏主按钮；改密自动同步
- **TOTP 动态验证码（RFC 6238）**：粘贴 Base32 密钥或 otpauth:// 链接；所有列表行内直显当前 6 位码 + 30 秒倒计时环；点击复制自动清除
- **安全体检 2.0（ECharts）**：评分环 + 风险条形图；弱/重复/长期未换/http/可加 2FA 五类清单，直达整改
- **自动快照**：每日首解锁 + 危险操作前强制；滚动保留 10 份；一键恢复（先留安全快照）
- **回收站**：30 天软删可恢复
- **自动输入**：向前台外部窗口键入 账号→TAB→密码→ENTER（Z 序回溯、焦点守护、IME 守护、提权窗口探测）；多账号候选面板
- **加密备份（.mdvault）**：独立备份密码，合并/覆盖恢复；**备份包含 TOTP 密钥**
- **忘记主密码向导**：自检恢复路径（Hello/恢复密钥/备份重建/归档重建）；恢复密钥会话在改密前限制敏感操作
- **QuickAction 接入**：选中凭据文本 → 自动识别预填新建
- **Popup 取密模式**：480px 以下单栏取密流——即搜即得、键盘全程、行内复制/TOTP/填入

## 设计取舍（移除）

- 嵌套文件夹树（改为 1 层文件夹+标签）、窗口匹配关键词、自定义键入序列、域隔离、一切自动弹出的引导——淹没主流程的 v1 概念
- v1 数据兼容（见上文说明）

</details>

---

# v1.4.1 Release Notes (2026-08-27)

## Fixes

- **Auto-Type Guide Could Not Be Dismissed (F037)**: the first-use guide no longer stacks on top of the candidate panel (it opens alone; candidates start only after "Got it"); closable via ESC / X / backdrop / button; if the settings write fails (mixed versions), a session-level flag prevents re-popping within the same session
- **Modal Hardening (F037)**: all 13 modal layers now support ESC + X + backdrop close (busy-sensitive operations are protected during in-flight requests); only one modal opens at a time
- **Version Mismatch Guard (F037)**: the UI compares its version with the data engine's and shows a persistent amber banner when they differ (mixed installs); Settings displays both versions; the build now fails if the frontend version constant drifts from package.json

## Changes

- **Editor Folder Field Removed (decision 8)**: new entries no longer offer a folder picker — organize by dragging entries onto the folder tree; existing entries keep their folder when edited (field data and RPC untouched)

<details>
<summary>中文说明</summary>

# v1.4.1 更新说明 (2026-08-27)

## 修复

- **首次引导弹窗关不掉（F037）**：引导不再与候选层叠加（单独弹出，点「我知道了」后才进入候选）；ESC / 右上角 X / 遮罩 / 按钮四路均可关闭；设置写入失败（混合版本）时会话内不再重复弹
- **弹窗体系加固（F037）**：全部 13 个弹层支持 ESC + X + 遮罩三通道关闭（进行中的敏感操作受保护）；同时只允许一个弹层
- **版本不一致防护（F037）**：界面与数据引擎版本不一致时顶部黄条常驻警告（混合安装场景）；设置页展示双版本；前端版本常量与 package.json 不一致时构建直接报错

## 变更

- **编辑器移除文件夹选择（决策 8）**：新建条目不再提供文件夹下拉，归类通过列表页拖拽完成；编辑已有条目时归类保持不变（字段与 RPC 保留）

</details>

---

# v1.4.0 Release Notes (2026-08-25)

## New Features

- **Data Directory Separation (F035, P0)**: vault data now lives at `%APPDATA%/my-desktop-tools/plugin-data/password-manager/` (outside the install folder), so uninstalling/reinstalling the plugin never touches it; a `.mdt-data` marker is written for future Core-side warnings
- **Automatic Legacy Migration (F035)**: on startup, data found in the old install-folder location is copied to the new directory (verified by size + SQLite magic), then the originals are kept renamed `.migrated` — nothing is ever deleted; if migration fails (permissions/disk), the plugin falls back to the old location so data stays accessible
- **In-App Info Bubbles (F036)**: ⓘ tooltips across the UI explain every feature — toolbar buttons, copy & clipboard auto-clear, default-account badge, editor advanced fields, .mdvault vs plaintext CSV, health-check categories, trash retention; hover or tap, dark-mode aware, edge-flipping
- **First-Use Onboarding (F036)**: a one-time 3-step getting-started card (organize → copy/auto-type → recovery key + backup) with Skip / Don't-show-again
- **Advanced Entry Fields (F036)**: window match keywords, custom auto-type sequence, and account domain isolation are now editable in the entry editor's Advanced section

<details>
<summary>中文说明</summary>

# v1.4.0 更新说明 (2026-08-25)

## 新增功能

- **数据目录分离（F035，P0）**：保险库数据改存 `%APPDATA%/my-desktop-tools/plugin-data/password-manager/`（安装目录之外），卸载/重装插件不再影响数据；写入 `.mdt-data` 标记供 Core 卸载警示判断
- **旧数据自动迁移（F035）**：启动时检测安装目录内的旧数据，复制到新目录（按大小 + SQLite 魔数校验）后旧文件改名 `.migrated` 保留——绝不删除任何内容；迁移失败（权限/磁盘）自动回退旧目录，数据始终可访问
- **应用内说明气泡（F036）**：全界面 ⓘ 气泡逐一讲解功能用法——工具栏按钮、复制与剪贴板自动清除、默认账号徽标、编辑器高级字段、.mdvault 与明文 CSV 区别、体检三类风险、回收站保留规则；悬停/点击均可，暗黑适配，边缘自动翻转
- **首次上手引导（F036）**：一次性三步引导卡（归类 → 复制/自动填入 → 恢复密钥+备份），可跳过/不再提示
- **条目高级字段（F036）**：窗口匹配关键词、自定义键入序列、账号域隔离可在编辑器「高级」区直接配置

</details>

---

# v1.3.0 Release Notes (2026-08-19)

## New Features

- **Folder Tree Interactions (F034)**: context menu (right-click or hover ⋯ button) on folders with New subfolder / Rename / Move to… / Move to top / Delete; a tree picker dialog with in-place folder creation (self & descendants greyed out, cycle-proof); full path breadcrumbs in the details pane and compact path hints on search results
- **Drag & Drop**: drag entries onto folders to move them, drag folders onto folders to re-parent, drop on the nav area to move to top level; illegal targets (self/descendant) highlight red and are rejected
- **Collapse Persistence**: folder tree expand/collapse state is saved in settings.json and restored across restarts
- **Depth Guard UX**: the 5th level hides the "New subfolder" action; server-side depth errors stay guarded
- **Delete Confirmation Stats**: deleting a folder now shows "contains N entries, M subfolders; entries move to uncategorized, subfolders move up one level"

## Fixes

- **Auto-Type Self-Capture (F030)**: when the foreground window belongs to the plugin or the host app, the target now walks up the Z-order (skipping own-process-chain / invisible / empty-title / tool windows, up to 5 levels) to pick the most recently active external window, instead of matching against the plugin's own window
- **Auto-Type Guidance**: the toolbar button shows a 3-step tooltip; a one-time first-use guide dialog is shown (remembered in settings); a "Recapture" action appears after the 10s target TTL expires

<details>
<summary>中文说明</summary>

# v1.3.0 更新说明 (2026-08-19)

## 新增功能

- **文件夹树交互（F034）**：文件夹右键菜单与悬停 ⋯ 按钮（新建子文件夹 / 重命名 / 移动到… / 移至顶层 / 删除）；「移动到…」树形选择弹窗，支持就地新建（自身与子孙置灰防环）；详情页完整路径面包屑，搜索结果行尾路径小字
- **拖拽**：条目拖到文件夹 = 移动条目；文件夹拖到文件夹 = 调整层级；拖到导航区空白 = 移至顶层；非法目标（自身/子孙）红色高亮拒绝
- **折叠持久化**：文件夹树展开/收起状态保存于 settings.json，重启后保留
- **深度上限 UX**：第 5 层不出现「新建子文件夹」入口，服务端深度校验兑底
- **删除确认统计**：删除文件夹前展示「含 N 个条目、M 个子文件夹；删除后条目移至未分类、子文件夹上浮一级」

## 修复

- **自动输入自捕获（F030）**：前台为插件/宿主自身窗口时，沿 Z 序回溯（跳过自身进程链/不可见/空标题/工具窗口，最多 5 层）取最近活动的外部窗口，不再拿自己的窗口做匹配
- **自动输入引导**：工具栏按钮展示三步悬浮提示；首次使用弹出一次性引导弹窗（settings 标记记忆）；10 秒目标过期后提供「重新捕获」入口

</details>

---

# v1.2.1 Release Notes (2026-08-18)

## Maintenance
- Version sync release: no functional changes since v1.2.0

<details>
<summary>中文说明</summary>

# v1.2.1 更新说明 (2026-08-18)

## 维护
- 版本同步发布：自 v1.2.0 以来无功能性变更

</details>

---

# v1.2.0 Release Notes (2026-08-17)

## Maintenance
- Added bilingual metadata (purpose/useCases/longDescription/features) via metadata.json to enrich marketplace detail display
- Version sync release: no functional changes since v1.1.0

<details>
<summary>中文说明</summary>

# v1.2.0 更新说明 (2026-08-17)

## 维护
- 新增 metadata.json 双语元数据（purpose/useCases/longDescription/features），丰富商城详情弹窗展示
- 版本同步发布：自 v1.1.0 以来无功能性变更

</details>

---

# v1.1.0 Release Notes (2026-08-16)

## New Features

- **Recovery Key (F033)**: 160-bit CSPRNG recovery key (Base32, 8 groups × 4 chars), shown once; unlocks the vault when the master password is forgotten and forces a master password reset. Regenerating invalidates the old key immediately
- **Forgot-Password Wizard (F032)**: lock-screen "Forgot master password?" entry self-checks available paths — Windows Hello / recovery key / rebuild-from-backup / rebuild (old vault is archived to `backups/vault-orphaned-*.db`, never deleted)
- **Import Old Vault**: after a rebuild, Settings can decrypt an archived vault with the old master password and merge entries back (dedup by title + username)
- **Reset Without Current Password (F020)**: sessions unlocked via a recovery method can reset the master password without the old one; copy/export/auto-type are paused until reset completes
- **Lock-Screen Hint Fix**: hint visibility no longer deadlocked behind the unlock-only Settings page; hint is revealed on click (shoulder-surfing safe); empty-hint setup now asks for confirmation

## Fixes

- Lock-screen hint no longer requires unlocking to toggle visibility (showHint now defaults on; explicit off in old settings.json is still respected)

<details>
<summary>中文说明</summary>

# v1.1.0 更新说明 (2026-08-16)

## 新增功能

- **恢复密钥（F033）**：160-bit CSPRNG 恢复密钥（Base32，8 组×4 字符），仅显示一次；忘记主密码时可解锁并强制重设主密码；重新生成后旧钥立即作废
- **忘记主密码向导（F032）**：锁屏「忘记主密码？」入口自检可用路径 —— Windows Hello / 恢复密钥 / 重建并从备份恢复 / 重建（旧库归档为 `backups/vault-orphaned-*.db`，绝不删除）
- **导入旧保险库**：重建后可在设置页用旧主密码解密归档库，按标题+用户名判重合并回数据
- **免当前密码重设（F020）**：经恢复方式解锁的会话可免旧密码重设主密码；重设完成前复制/导出/自动输入暂停
- **锁屏提示修复**：提示可见性不再死锁于需解锁才能进的设置页；提示点击才露出（防肩窥）；初始化留空提示时二次确认

## 修复

- 锁屏提示开关不再需要先解锁进设置才能生效（showHint 默认开启；老 settings.json 显式关闭仍被尊重）

</details>

---

# v1.0.0 Release Notes (2026-08-14)

## New Features

- **Zero-Knowledge Vault**: Master password (Argon2id) + AES-256-GCM field-level encryption, keys never touch disk
- **Entry Management**: CRUD for login entries with title / username / password / URL / notes / folder / tags / favorite
- **Search & Groups**: fuzzy search over title/username/URL, favorites and recent-use groups
- **Password Generator**: random password / passphrase / PIN with live entropy estimation
- **Clipboard Guard**: copy with countdown auto-clear (default 30s)
- **Auto Lock**: idle timeout lock (default 5 min) with in-memory plaintext wiped on lock
- **Encrypted Backup**: export/restore the whole vault as an `.mdvault` file (merge or overwrite)
- **Responsive UI**: 3-pane (≥860px) / 2-pane (480-860px) / single-pane quick-copy flow (<480px)
- **Windows Hello Unlock**: optional DPAPI-protected quick unlock (off by default, opt-in)
- **Security Dashboard**: health score with weak / reused / stale password findings
- **Trash & History**: 30-day recycle bin, password history snapshots with rollback
- **CSV Import/Export**: Chrome / Edge / Bitwarden import, plaintext export with re-verification
- **Auto-Type**: fill credentials into the previous foreground window (username → TAB → password → ENTER)
- **Default Account**: mark a default account per site, aggregated by eTLD+1

<details>
<summary>中文说明</summary>

# v1.0.0 更新说明 (2026-08-14)

## 新增功能

- **零知识保险库**：主密码（Argon2id）+ AES-256-GCM 字段级加密，密钥永不落盘
- **条目管理**：登录类条目增删改查，支持标题 / 用户名 / 密码 / URL / 备注 / 文件夹 / 标签 / 收藏
- **搜索与分组**：标题/用户名/URL 模糊搜索，收藏与最近使用分组
- **密码生成器**：随机密码 / 密码短语 / PIN，实时熵评估
- **剪贴板守护**：复制后倒计时自动清除（默认 30 秒）
- **自动锁定**：闲置超时锁定（默认 5 分钟），锁定即清空内存明文
- **加密备份**：全库导出/恢复 `.mdvault` 加密文件（支持合并/覆盖）
- **响应式界面**：≥860px 三栏 / 480-860px 双栏 / <480px 单栏快速取密流
- **Windows Hello 解锁**：可选 DPAPI 保护的快速解锁（默认关闭，需显式开启）
- **安全仪表盘**：健康评分 + 弱密码 / 重复密码 / 长期未更换检测
- **回收站与历史**：30 天回收站，密码历史快照与回滚
- **CSV 导入导出**：Chrome / Edge / Bitwarden 格式导入，明文导出需二次验证
- **自动输入**：向前台窗口键入凭据（账号 → TAB → 密码 → ENTER）
- **默认账号**：按站点（eTLD+1）标记默认账号，候选列表预选

</details>
