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
