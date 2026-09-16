# v1.3.0 更新说明 (2026-09-16)

## 优化
- 代码规范与导入结构清理，随核心 1.0 生态整体质量加固

---

# Changelog

## v1.2.0 (2026-09-05)

### 新增

- **QuickAction 上下文联动（M12）★**：manifest contextMenu 7 直达条目（智能识别/Base64 解码/JWT 解析/SHA-256/URL 解码/Hex 解码/AES 解密，全部带 dataTypes 过滤）；Sidecar 新增 context-data-available（按选中内容智能改写 QA 操作名，如「识别为 JWT · 点击解析」）/ context-action-execute（内存缓存零痕迹）/ get_pending_context（一次性拉取）三方法；前端双通道接收（Core postMessage + RPC 兜底，指纹去重）+ actionId 路由——编码类/JWT/哈希/识别开窗即出结果，AES 预填密文与解密方向待用户输密钥；supportedTypes 扩展 plaintext/base64/url/json；QA 条目名「智能识别」→「加密解密·智能识别」（动作名带插件身份前缀）
- **SM2 国密工具箱（M14）**：GB/T 32918 全套——密钥对生成（PKCS#8/SPKI PEM + 裸 hex，瞬时完成）；加解密（C1‖C3‖C2，SM3 KDF，C3 校验失败统一话术）；签名验签（64B r‖s，用户 ID 参与 ZA 默认 1234567812345678）；密钥信息解析。签名用 sm2 crate 官方 dsa；PKE 按国标手写（sm2 0.13 已移除 pke）并以 round-trip/篡改/换钥单测验证
- **工具帮助系统（M13/F062）**：23 个工具的五段式说明（简介/来源与标准/怎么用/选项区别/安全提示）内容库；顶栏 ？按钮看当前工具 + 编码类工具头 ？就地弹层；点外部/Esc/× 关闭，不占功能区
- **UI 图标化**：全量 emoji → lucide 图标（@lucide/vue，分类/导航/工具栏/按钮/横幅/Tab）；NavTree 重构（搜索图标/折叠箭头/收藏星标/分类图标/选中指示条）；运行按钮加载态旋转动画；插件图标资产 icon.svg + icon.png（scripts/gen-icon.mjs 程序化可复现）；metadata.json 双语填充；build-zip 补 icon.png 打包

### 优化

- **解析速度**：即算防抖自适应（≤8KB 输入 300ms→120ms）；QA 探测 4KB 采样保证 400ms deadline 内返回

### 修复

- **工作区标签页（M13）**：打开的工具自动成 tab（点击切换 / × 与中键关闭 / 关闭激活时相邻激活）；KeepAlive 缓存面板实例——切换工具不丢操作内容（JWT 解码结果、哈希勾选、识别候选等全部保留）；预填通道与快捷键监听做激活期适配，关闭 tab 即释放缓存内存
- **管理入口上收顶栏 + 右侧边栏（M13）**：NavTree「管理」分组移除；顶栏独立图标（历史/设置）直开对应功能，内容显示在右侧 320px 可收起边栏（同图标再点或 X 收起，收起后工作台占满；收藏不设顶栏入口，由导航常用区承载）；HistoryPanel 重构为 section 驱动，历史卡片窄栏三行布局适配边栏宽度；history-settings 不再占工作台（旧收藏 id 自动转开边栏）；标签页条置于工作台顶部（不压导航）；导航 41px 对齐基线统一（分类标题/工具项/常用区文本同列、选中指示条移至箭头列、常用区行补收藏星标）；⚡📦 残留图标 lucide 化，模板 emoji 全量清零
- **帮助入口全面化**：12 个独立面板（哈希/对称/经典/压缩/生成器/识别/文件/RSA/SM2/JWT/KDF/文件加密）首行各加「说明」按钮（flex order:99 恒行尾右对齐），与顶栏 ？、工具头 ？ 共三入口；标签页条支持右键菜单（关闭左侧/关闭右侧/关闭所有，首尾项自动禁用）；🗜🔤📊 等最后一批 emoji 图标归零
- **QA 直达自动复制结果（M13/F062 配套）**：QA 右键直达（Base64/URL/Hex 解码、SHA-256）成功后结果自动进入剪贴板——「选中→右键→解码→粘贴」三步闭环；设置边栏新增开关（默认开，带剪贴板留痕提示）；JWT/AES 类结果不自动复制；transform_run 失败时清空旧结果防误复制
- **QA 解码直达容错路由**：Base64/URL/Hex/JWT 直达前先跑识别引擎（4KB 采样），目标类型未命中（低置信以下）自动改走智能识别页并给出候选，不再直接报解码错误；识别 RPC 失败时按用户选择直达（fail-open）
- **QA 右键菜单动态化（核心 v1.7 契约首批接入）**：context-data-available 探测命中时仅返回 Top-2 相关条目（类型直达 + 智能识别；base32/base58 归入 Base64 解码、htmlEntity/unicodeEscape 归入 URL 解码、byteStr2 归入 Hex 解码），无命中不带字段回退 manifest 全量 7 条；actionId 共用既有执行链路，前端路由零改动
- **QA 直达同工具内容滞留修复**：核心复用窗口后，QA 直达的目标 tab 若「已打开且激活」，预填通道写入无人消费（onMounted/onActivated 不再触发）导致窗口内容停留在旧值——pendingInput/pendingKeyIv 通道改 reactive 并新增 watchPendingInput/watchPendingKeyIv（写入即消费，幂等），五面板接入；同族修复生成器「填入对称加密」到已激活对称页失效的问题
- 挂载即算缺陷：识别跳转/预填输入后工具不自动运行（ToolCanvas watch 补 immediate + 空输入守卫）


## v1.1.0 (2026-08-29)

### 新增

- **RSA 工具箱（M8）**：密钥生成作业（1024-4096 位，进度阶段可取消，PKCS#8/#1 + SPKI）；加解密 PKCS1v15/OAEP-SHA256 分段（k-11/k-34 块上限，解密定长块校验）；签名验签 PKCS1v15 + PSS（salt=hash 长，SHA-256/384/512，验签无效非报错态）；密钥信息解析（位数/exponent/modulus + 模糊不 panic）。与 OpenSSL（Node crypto）双向互解/互验 9 项交叉全部一致
- **JWT 工具箱（M8）**：解码（三段 + claims 时间人类可读 + 过期徽标 + 未验签警示）/ HS256·384·512 签发（与 Node crypto HMAC 逐字一致）/验签（badSignature|expired|malformed 三态，常数时间比较）
- **KDF 密钥派生（M9）**：PBKDF2（RFC 6070 向量、迭代上限 10^7、与 Node crypto.pbkdf2Sync 交叉一致）/ Argon2id（PHC 标准串 RFC 9106 字母表 + OWASP 推荐参数一键）/ OsRng salt 生成
- **文件加密（M10）★**：.mydte 容器（49B 头：MYDTE1/版本/算法/KDF/Argon2 参数/salt16/nonce12 + AES-256-GCM，AAD=头部防篡改）；头部零明文元数据；解密嗅探建议扩展名；错密码统一话术；200MB 实测加密 3.7s/解密 3.3s（门槛 30s）
- **前端**：P11 RSA 页（4 Tab）/P12 JWT 页（3 Tab）/P13 文件加密页（2 Tab，强度联动）/KDF 页；工具注册表补全 V1.0 遗留缺失的面板类条目（导航可达）；智能识别 JWT 跳转直达解码页并自动解密；standalone 面板预填通道（usePendingInput）

### 修复

- 上传上限放宽 200MB→201MB（含 .mydte 容器头部/tag 开销余量，修复 200MB 原文件加密后无法回传解密的边界）
- 解密结果文件名双重扩展名（photo.png.mydte → photo.png 而非 photo.png.png）

## v1.0.0 (2026-08-29)

### 新增

- **编码转换（M1）**：Base64（标准/URL-safe/无填充/宽容解码/76 换行）、Hex（大小写/分组/0x）、Base32（RFC4648+Hex）、Base58、Base62（手写大整数）、Base85（Ascii85 z/y 紧缩+Z85）、URL 三模式、HTML 实体、Unicode 转义（\u 代理对/U+/&#x）、进制字节串（2/8/10）、摩斯电码（.- 与 ·− 双风格）——输入即算 300ms 防抖
- **格式徽章（F012）**：TEXT/HEX/BASE64 三态徽章在输入/输出/密钥三处独立，支持 Hex→Base64 直转
- **哈希摘要（M2）**：12 算法同屏（MD5/SHA-1/224/256/384/512/SHA3 全系/SM3/CRC32）、HMAC 六算法（RFC 4231 向量）、加盐、比对；文件哈希流式 4MB 块（100MB 与 certutil 逐位一致）
- **对称加密（M3）**：AES 三层引擎（AEAD/流式/分组 × PKCS7/Zero/None 手写填充）、DES/3DES（K1=K3 两密钥）、RC4（手写 KSA+PRGA，RFC 6229）、Blowfish、ChaCha20（RFC 8439 §2.4.2）/XChaCha20/Poly1305 AEAD、SM4（GB/T 32907）、XOR；AES-GCM/CBC 与 OpenSSL 双向交叉验证；错误三分类（paddingInvalid/tagVerifyFailed/keyLenMismatch）
- **经典密码（M4）**：凯撒（25 组全位移枚举）/ROT13/47/N/维吉尼亚/Atbash（数字镜像）/栅栏/培根（24/26 表）/A1Z26/简单替换（映射表编辑+随机重掷+密钥词生成）
- **压缩与文件互转（M5）★**：gzip/zlib/deflate（flate2 rust backend）/brotli/lz4 Frame + AUTO 探测；文件→压缩字符串→还原文件 round-trip（50MB SHA-256 逐位一致）；512MB 炸弹防护；魔数嗅探 18 类；对比全部算法
- **生成器（M6）**：密码（OsRng+拒绝采样）/UUID v4/随机字节/密钥套件（→填入加密面板）/强度评估（熵/五档/量级化破解时间/Top100+键盘序列弱模式）
- **智能识别（M7）**：15 类特征规则 + 置信度排序候选卡 + 跳转预填（落地即可运行）
- **文件管线**：256KB 分块上传（10 分钟过期/原子改名）+ 单 worker 作业（进度/协作取消）+ 结果 256KB 分块回传 + rfd 保存对话框（token 轮询）
- **持久层**：历史（仅元数据，FIFO 100）/收藏/设置；config.json 原子写；零痕迹铁律（明文/密钥/内容永不落盘）
- **架构**：一切 ≤4MB 文本走统一 transform_run 分发器（tagged enum）；Sidecar stderr 只写元数据日志
