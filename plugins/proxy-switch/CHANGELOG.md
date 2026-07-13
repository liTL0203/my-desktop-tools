# v2.4.0 更新说明 (2026-06-05)

## Bug 修复
- TUN 适配器生命周期深度修复：解决插件关闭时适配器被删除的问题
  - 深层根因：wintun 设计中 `WintunCloseAdapter` 会移除 `WintunCreateAdapter` 创建的适配器，无法跨进程持久化
  - 修复：使用固定 GUID 创建适配器，Windows 按 GUID 记忆 IP 配置，每次启用时通过相同 GUID 重建（存在则打开，不存在则创建）
  - `shutdown()` 主动释放适配器句柄，`resume()` 通过固定 GUID 重建适配器并检查 IP 是否已自动恢复
  - `cmd_delete_tun_adapter` 简化为丢弃 TunRuntime（wintun 自动移除）
  - 新增 `TUN_ADAPTER_GUID` 固定常量，确保适配器身份和 IP 配置跨重启一致

---

# v2.3.0 更新说明 (2026-06-05)

## Bug 修复
- TUN 适配器生命周期修复（初版）：新增 `TunRuntime::disable()` / `resume()` 方法
  - 根因：`disable_proxy_background` 中 `*tun = None` 触发 Arc 级联 drop
  - `cmd_enable_proxy` 支持检测已禁用的 TunRuntime 并调用 resume 复用
  - 抽取 `spawn_accept_loop` 公共函数，start/resume 共享接受循环逻辑

---

# v2.0.0 更新说明 (2026-06-05)

## 重构
- 从系统代理模式重构为 TUN 模式（虚拟网卡拦截）
- 100% 全局流量劫持，覆盖不走系统代理的程序（游戏、CLI 工具等）

## 新增
- TUN 虚拟网卡管理（基于 WinTun 驱动）
- 流量链功能（多级代理串联）
- 本地 DNS 服务器 (127.0.0.1:53) + DNS 中继 + DNS 劫持 + 持久化缓存
- DNS 缓存管理 RPC 接口（list/clear/delete/update）
- WinTun 驱动一键安装/更新/卸载/版本检测
- 节点管理（HTTP/SOCKS5/VPN/链式代理）
- 规则引擎升级（域名后缀、关键词、端口、协议、进程匹配）
- 仪表盘状态监控
- 规则导入/导出（AutoProxy/SwitchyOmega/纯文本）

## 移除
- 移除旧版系统代理模式（仅修改 WinInet 设置）
- 死代码清理（~2860 行，6 个文件）

## 安全修复
- 命名管道访问权限：NULL DACL 替换为 Authenticated Users + SYSTEM DACL，防止任意进程连接提权 sidecar
- URL 打开命令注入防护：仅允许 http/https 协议，使用 ShellExecuteW 替代 cmd /c start
- 安全描述符内存泄漏修复：Box::leak 替换为 PipeSecurity 结构体持有所有权

## Bug 修复
- IPv6 路由恢复完整实现（恢复备份路由而非仅删除默认路由）
- IPv6 路由表独立解析逻辑（无子网掩码格式）
- OnceLock 缓存改为可重置（DNS 地址 + 物理网卡 IP/索引，支持网络变更时刷新）
- 假 IP 分配冲突检测（253 次循环避免 IP 复用冲突）
- 配置文件原子写入（先写 .tmp 再 rename，崩溃不损坏文件）
- save_config 字段处理明确化（enabled/dns 由独立 RPC 管理）

## 健壮性增强
- DNS relay 重试机制（3s 超时后重试一次）
- HTTP CONNECT 响应解析：解析 HTTP 状态行提取状态码，替代宽松字符串匹配
- SOCKS5 代理：支持 RFC 1929 Username/Password 认证 + IPv6 地址支持
- DNS 查询解析支持压缩指针 (0xC0)
- DNS 响应解析增加边界检查和标签长度校验

---

# v1.2.0 更新说明 (2026-05-05)

## 新增
- 支持规则自动切换
- 多 Profile 管理
- 自动启动功能

## 优化
- 优化代理检测速度
- 改进系统托盘交互

## 修复
- 修复 Windows 代理设置失败问题

---

# v1.1.0 更新说明 (2026-04-15)

## 新增
- 系统级代理管理
- 代理规则配置

---

# v1.0.0 更新说明 (2026-04-01)

## 新增
- 初始版本
- 基础代理切换功能
