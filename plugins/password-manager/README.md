# 密码管理器 v2.0（M1）用户说明 / Password Manager v2.0 (M1)

> 本地零知识加密密码保险库——重写版 M1 里程碑。主密码派生密钥 + AES-256-GCM 字段级加密，数据永不出设备。
> Local zero-knowledge password vault (v2 rewrite, milestone M1). Master-password key derivation + AES-256-GCM field-level encryption; data never leaves your device.

## 功能（v2.0 完整版 = M1 + M2）

- **零知识加密保险库**：标题/账号/密码/网址/备注/标签/自定义字段全部 AES-256-GCM 加密落盘，密钥由主密码派生（Argon2id），永不明文存储。主密码丢失无法找回任何数据（设计使然）
- **创建向导**：主密码强度实时评估 + 恢复密钥内嵌生成（160-bit，仅显示一次，离线抄写保管；可跳过需确认风险）
- **解锁与锁定**：防暴力延迟（连续失败 5 次起递增等待）、闲置自动锁定（默认 5 分钟，可调）、Ctrl+L 手动锁定
- **条目管理**：标题/用户名/密码/网址（自动补 https://）/备注/收藏；**自定义字段**（key-value，可标记「密码型」遮蔽显示、复制走自动清除通道）
- **组织**：一层文件夹（编辑器内下拉可选、可就地新建）+ 标签 + 收藏 + 最近使用 + 默认账号（同站点唯一，eTLD+1 聚合，列表置顶）
- **搜索**：标题/账号/网址/标签/自定义字段名即时过滤，支持拼音首字母（如「淘宝」输 tb）
- **密码生成器**：随机密码 / 口令短语（EFF 词表）/ PIN，实时熵与强度评估；锁屏态亦可使用
- **剪贴板守护**：条目内复制后倒计时自动清空（默认 30 秒，可调）；你在此期间复制了其他内容则自动让路
- **密码历史**：改密自动留痕（每条目最多 10 条），详情侧滑可查看
- **加密备份**：全库导出为 .mdvault 加密文件（备份密码独立于主密码）；恢复支持合并（标题+账号判重跳过）与覆盖（自动先留档当前库）
- **忘记主密码**：锁屏「忘记主密码？」→ 用恢复密钥解锁
- **Windows Hello 快速解锁**：指纹 / PIN 秒解（DPAPI 绑定当前 Windows 用户；设置页开关，启用需主密码验证；失效自动回退主密码）
- **TOTP 动态验证码**：条目绑定验证器密钥（Base32 / otpauth:// 链接粘贴即用，SHA1/SHA256），列表行内直显当前码 + 30 秒倒计时环（剩 5 秒变红），点击复制
- **Popup 取密流**（默认独立小窗 400×560）：打开即搜索、↑↓ 选择、Enter 复制密码、Alt+Enter 复制账号、⌨ 一键填入前台窗口
- **安全体检 2.0**：健康评分 + 五类风险（弱密码 / 重复密码 / 长期未更换 / http 明文站 / 可加 2FA 未加）+ 每条带「去修改」整改入口
- **自动快照**：每日首次解锁自动快照，改密 / 覆盖恢复 / 快照恢复前强制快照；设置页可查看 / 立即快照 / 一键恢复（滚动保留 10 份）
- **回收站**：删除进回收站（30 天自动清除），可一键恢复到原位置
- **自动输入（Auto-Type）**：点目标程序输入框 → 回插件点「⌨ 填入前台」（10 秒内）→ 自动键入 账号→TAB→密码→ENTER；多账号出候选列表（数字键快选）；焦点被抢 / 管理员窗口自动中止并提示
- **修改主密码**：验证旧密码 → 重包裹密钥（不重加密数据）→ 自动先快照；Hello 缓存同步刷新
- **忘记主密码向导**：自检四条恢复路径（Hello / 恢复密钥 / 从备份重建 / 归档重建空库），旧库归档永不删除
- **QA 快速保存**：选中文本（账号/密码/网址）→ 中键 → 「保存到密码管理器」→ 自动识别凭据并打开编辑器预填
- **键盘流**：↑↓ 选择、Enter 复制密码、Alt+Enter 复制账号、Ctrl+F 搜索、Ctrl+N 新建、Ctrl+L 锁定

## 重要说明

- **不兼容 v1 数据**：v2 是全新实现的保险库格式。若数据目录存在旧版库文件，v2 会将其**自动改名隔离**（`vault-legacy-incompatible-*.db`，不读取不删除），并按全新保险库开始。
- **数据目录**：`%APPDATA%\my-desktop-tools\plugin-data\password-manager\`（vault.db / settings.json / backups/），独立于插件安装目录，卸载重装不影响数据。
- **恢复密钥解锁会话限制**：经恢复密钥解锁后，复制 / 导出 / 自动输入暂停，重设主密码后恢复（防数据与失控密钥共存）。

## Features (English, M1)

- Zero-knowledge vault: every sensitive field encrypted (AES-256-GCM), keys derived via Argon2id, never stored in plaintext
- Setup wizard with live strength meter and one-time 160-bit recovery key (offline keep)
- Brute-force throttling, idle auto-lock, manual lock (Ctrl+L)
- Entries with custom fields (secret masking + guarded copy), folders (inline create), tags, favorites, recents, per-site default account
- Instant search incl. Chinese pinyin initials; password generator (random / passphrase / PIN) with entropy meter, usable from the lock screen
- Clipboard guard with countdown auto-clear and user-copy yield
- Encrypted .mdvault backup export / restore (merge or overwrite with automatic pre-restore snapshot)
- Password history (last 10 per entry)

**v1 data is not compatible**: legacy vault files are quarantined (renamed, never read or deleted) and v2 starts fresh.

---

## ⚠️ Disclaimer

- **"AS IS"**: This software is provided "AS IS", without any express or implied warranty, including but not limited to merchantability, fitness for a particular purpose, and non-infringement.
- **Use at Your Own Risk**: The developer shall not be liable for any direct or indirect losses (including but not limited to data loss, system damage, business interruption) caused by the use of this software. Users must assess and bear all risks.
- **Data Backup**: It is recommended to back up important data before using this software to prevent irreversible loss.
- **Compatibility Risks**: This software may have unknown defects or be incompatible with certain system environments, hardware configurations, or third-party software. The developer does not guarantee normal operation in all environments.
- **Plugin Disclaimer**: Plugins in this application are independent modules. The developer makes no guarantee regarding the behavior, security, or stability of third-party plugins. Users must assess and bear the risks of using third-party plugins.

> Downloading or using this software indicates that you have read and agree to the above disclaimer.
