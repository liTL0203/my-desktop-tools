# Password Manager

> Local zero-knowledge password vault plugin — master password encryption (Argon2id + AES-256-GCM), quick unlock, password generator, health dashboard, and Auto-Type.

## Features

- **Zero-Knowledge Vault**: All sensitive fields are encrypted with AES-256-GCM; the key is derived from your master password (Argon2id) and never written to disk. Losing the master password means the data cannot be recovered — by design
- **Master Password Unlock/Lock**: full-state machine with brute-force throttling and idle auto-lock (default 5 minutes)
- **Entries, Folders & Tags**: login entries with title / username / password / URL / notes, organized by folders and tags
- **Search / Favorites / Recent**: instant fuzzy search, pinned favorites, recent-use grouping
- **Password Generator**: random password, passphrase, or PIN with live entropy meter
- **Clipboard Guard**: every copy starts a visible countdown that wipes the clipboard (default 30s)
- **Encrypted Backup (.mdvault)**: export the whole vault to an encrypted file; restore on any machine with merge or overwrite modes
- **Windows Hello Quick Unlock** (optional, off by default): DPAPI-protected key cache for instant unlock
- **Security Dashboard**: health score plus weak / reused / stale password findings and fix guidance
- **Trash & Password History**: deleted entries stay 30 days; every password change is snapshotted (last 20) and can be rolled back
- **CSV Import/Export**: import from Chrome / Edge / Bitwarden; plaintext export requires re-entering the master password
- **Auto-Type**: "Fill into previous window" fills username → TAB → password → ENTER into the window that was focused before the popup opened
- **Default Account**: mark one default account per site (eTLD+1) for quick selection
- **Recovery Key**: one-time 160-bit recovery key (shown once, keep offline) unlocks the vault when you forget the master password, then forces a master password reset
- **Forgot-Password Wizard**: lock-screen self-check offers every recovery option available on this machine (Hello / recovery key / rebuild from backup / rebuild with archive — the old vault is archived, never deleted)

## Usage

1. Open My Desktop Tools and launch "Password Manager" (popup opens by default)
2. On first run, create a master password (entered twice, with strength feedback and an unrecoverable warning)
3. Add entries, generate passwords, and organize them with folders, tags, and favorites
4. Copy any field — the clipboard clears automatically after the countdown
5. Export periodic `.mdvault` backups to a USB drive or another safe location

## Security Notes

- The vault lives in `%APPDATA%/my-desktop-tools/plugins/password-manager/vault.db`; sensitive fields are encrypted at rest
- Master password is never stored; there is no backdoor. **If the master password is lost and no recovery key or backup exists, the data cannot be recovered — we strongly recommend generating a recovery key and keeping it offline**
- Logs never contain passwords, usernames, titles, URLs, or notes — entry IDs and error codes only
- Auto-Type refuses to type when the foreground window changed between matching and typing (focus-guard)
- The recovery key is shown only once; after a rebuild the old vault is archived to `backups/vault-orphaned-*.db` (never deleted) and can be re-imported with the old master password

## Version History

| Version | Date | Notes |
|---------|------|-------|
| 1.1.0 | 2026-08-16 | Recovery key, forgot-password wizard, import old vault, reset without current password, lock-screen hint deadlock fix |
| 1.0.0 | 2026-08-14 | Initial release |

---

**Plugin ID**: password-manager
**Author**: My Desktop Tools

---

<details>
<summary>中文说明</summary>

# 密码管理器

> 本地零知识加密密码保险库插件 —— 主密码加密（Argon2id + AES-256-GCM）、快速解锁、密码生成器、安全仪表盘与自动输入。

## 功能介绍

- **零知识保险库**：所有敏感字段以 AES-256-GCM 加密；密钥由主密码（Argon2id）派生，永不落盘。主密码丢失即数据无法恢复——这是设计使然
- **主密码解锁/锁定**：完整状态机，含防暴力递增延迟与闲置自动锁定（默认 5 分钟）
- **条目/文件夹/标签**：登录类条目（标题/用户名/密码/URL/备注），文件夹与标签双维度组织
- **搜索/收藏/最近**：即时模糊搜索、收藏置顶、最近使用分组
- **密码生成器**：随机密码/密码短语/PIN，实时熵评估
- **剪贴板守护**：每次复制启动可视倒计时，到点自动清空（默认 30 秒）
- **加密备份（.mdvault）**：全库导出为加密文件，可在任意机器恢复（合并/覆盖两种模式）
- **Windows Hello 快速解锁**（可选，默认关闭）：DPAPI 保护的密钥缓存，秒级解锁
- **安全仪表盘**：健康评分 + 弱密码/重复密码/长期未更换检测与整改引导
- **回收站与密码历史**：删除条目保留 30 天；每次改密留存快照（上限 20 条），可回滚
- **CSV 导入导出**：支持 Chrome/Edge/Bitwarden 导入；明文导出需再次输入主密码
- **自动输入**：「填入前台窗口」将 账号 → TAB → 密码 → ENTER 键入 popup 打开前的焦点窗口
- **默认账号**：按站点（eTLD+1）标记默认账号，快速预选
- **恢复密钥**：一次性 160-bit 恢复密钥（仅显示一次，离线保管），忘记主密码时可解锁并强制重设主密码
- **忘记主密码向导**：锁屏自检本机全部可用恢复方式（Hello / 恢复密钥 / 重建并从备份恢复 / 重建归档——旧库只归档不删除）

## 使用说明

1. 打开 My Desktop Tools，启动「密码管理器」（默认弹出小窗）
2. 首次使用需创建主密码（双次输入 + 强度评估 + 不可恢复警示）
3. 添加条目、生成密码，用文件夹/标签/收藏组织
4. 复制任意字段，剪贴板将在倒计时后自动清除
5. 定期导出 `.mdvault` 备份到 U 盘或其他安全位置

## 安全说明

- 保险库位于 `%APPDATA%/my-desktop-tools/plugins/password-manager/vault.db`，敏感字段静态加密
- 主密码不存储；没有后门。**主密码丢失且无恢复密钥/备份时数据不可恢复，强烈建议生成恢复密钥并离线保管**
- 日志绝不包含密码、用户名、标题、URL、备注——仅条目 ID 与错误码
- 自动输入在匹配与键入之间检测到前台窗口变化时会立即中止（焦点守护）
- 恢复密钥仅显示一次；重建后旧库归档为 `backups/vault-orphaned-*.db`（绝不删除），想起旧主密码时可导入恢复

</details>

---

## ⚠️ Disclaimer

- **"AS IS"**: This software is provided "AS IS", without any express or implied warranty, including but not limited to merchantability, fitness for a particular purpose, and non-infringement.
- **Use at Your Own Risk**: The developer shall not be liable for any direct or indirect losses (including but not limited to data loss, system damage, business interruption) caused by the use of this software. Users must assess and bear all risks.
- **Data Backup**: It is recommended to back up important data before using this software to prevent irreversible loss.
- **Compatibility Risks**: This software may have unknown defects or be incompatible with certain system environments, hardware configurations, or third-party software. The developer does not guarantee normal operation in all environments.
- **Plugin Disclaimer**: Plugins in this application are independent modules. The developer makes no guarantee regarding the behavior, security, or stability of third-party plugins. Users must assess and bear the risks of using third-party plugins.

> Downloading or using this software indicates that you have read and agree to the above disclaimer.
