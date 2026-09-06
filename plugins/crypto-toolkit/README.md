# 加密解密工具箱（crypto-toolkit）

> 本地密码学与压缩工具箱：70+ 功能覆盖编码 / 哈希 / 对称加密 / 非对称与 JWT / KDF / 文件加密 / 经典密码 / 压缩文件互转 / 生成器 / 智能识别，全部离线计算，零痕迹隐私。

## 功能介绍

### 编码转换（11 工具）
- **Base64**：标准 / URL-safe / 无填充；宽容解码（data: 前缀 / 换行 / 空格）；76 字符换行
- **Hex**：大小写 / 每 2 字符分组 / 0x 前缀
- **Base32 / Base58 / Base62 / Base85**（Ascii85 z/y 紧缩 + Z85）
- **URL 编码**：component / uri / 全部 %XX 三模式，对齐浏览器行为
- **HTML 实体 / Unicode 转义（\u 代理对）/ 进制字节串 / 摩斯电码**（·− 双风格）

### 哈希摘要
- **12 算法同屏**：MD5 / SHA 全系 / SHA3 全系 / SM3 国密 / CRC32
- **HMAC**（MD5/SHA 六算法）、加盐、哈希比对（宽容选项）
- **文件哈希**：拖入文件流式计算（≤200MB），进度实时可取消，与 certutil 一致

### 对称加密（7 算法）
- **AES**（128/192/256 × ECB/CBC/CFB128/OFB/CTR/GCM，PKCS7/Zero/None 手写填充）
- **DES / 3DES**（16B 两密钥 K1=K3 / 24B 三密钥）
- **ChaCha20 家族**（RFC 8439 计数器语义 / XChaCha20 / Poly1305 AEAD）
- **SM4 国密 / RC4 / Blowfish / XOR**
- 输出与 WebCrypto/OpenSSL 兼容（AEAD = ciphertext‖tag）；密钥/IV 独立徽章 + 一键生成套件

### 经典密码（8 种）
凯撒（含 25 组全位移枚举）/ ROT13/47/N / 维吉尼亚 / Atbash / 栅栏 / 培根（24/26 表）/ A1Z26 / 简单替换（随机表 + 密钥词生成）

### 压缩与文件互转 ★
- **字符串压缩**：gzip / zlib / deflate / brotli / lz4 + AUTO 自动探测
- **文件 → 压缩字符串**：任意文件压缩成 Base64 文本，复制粘贴即可发送
- **压缩字符串 → 文件**：粘贴或拖入 .txt，自动探测格式 + 魔数嗅探类型 + 建议扩展名保存
- 512MB 解压炸弹防护；收益建议（已压缩文件提示直接 Base64）

### 生成器
密码（字符集/易混淆排除/每集保证）、UUID v4 批量、随机字节、算法密钥套件（可一键填入加密面板）、密码强度评估（熵/五档/量级化破解时间/弱模式）

### 智能识别
粘贴未知内容 → 15 类特征规则分析 → 置信度排序候选卡 → 一键跳转对应工具并预填输入

### RSA 工具箱（V1.1）
- **密钥生成**：1024/2048/3072/4096 位作业生成（进度可取消），私钥 PKCS#8/PKCS#1 + 公钥 SPKI，PEM 可被 OpenSSL 导入
- **加解密**：PKCS#1 v1.5 / OAEP-SHA256，长输入自动分段（k-11 / k-34），与 OpenSSL 双向互解
- **签名验签**：PKCS1v15 + PSS（salt=hash 长），SHA-256/384/512；验签 ✅/❌ 非报错态，与 OpenSSL 互验
- **密钥信息**：类型/格式/位数/exponent/modulus hex，模糊输入不崩溃

### JWT 工具箱（V1.1）
- **解码**：三段解析 + JSON 美化 + exp/nbf/iat 人类可读（含「已过期 N 天」徽标）+ 未验签安全警示
- **签发**：HS256/384/512，与 jwt.io 逐字兼容
- **验签**：签名/过期/结构三态结果 + 一键互填

### 密钥派生 KDF（V1.1）
- **PBKDF2**：PRF SHA-256/512/SHA1，迭代至 10,000,000，RFC 6070 向量对齐，与 Node crypto 交叉一致
- **Argon2id**：m/t/p/dkLen 全参数，hex/base64 + PHC 标准串（RFC 9106 字母表），OWASP 推荐参数一键填充
- **salt 生成**：OsRng 随机 16B hex

### 文件加密 .mydte（V1.1）
- 任意文件（≤200MB）+ 密码 → Argon2id 派生密钥 → AES-256-GCM 容器（200MB 实测加密 3.7s）
- 容器头部不含文件名等任何明文元数据；AAD 防头部篡改
- 解密自动嗅探类型建议扩展名；密码错/损坏统一话术不泄露信息；强度评估联动

## 使用说明

1. 在插件管理中启用「加密解密工具箱」
2. 左侧导航树选择工具，右侧三段式布局（参数条 + 输入区 + 输出区）
3. **即算工具**（编码/哈希/经典）输入变化 300ms 自动计算；**显式运行工具**（加密/压缩/生成）点击 ▶ 运行或 Ctrl+Enter
4. **格式徽章**：输入/输出/密钥框各自独立声明 TEXT / HEX / BASE64 解释方式（Hex 输入 + Base64 工具 = 直转）
5. **⇄ 交换**：输出回填输入 + 方向反转 + 徽章传递
6. **文件操作**：拖入文件即可哈希/压缩/Base64；结果可复制（≤8MB）或 rfd 保存对话框导出

## 注意事项

- **零痕迹隐私**：密钥/明文/文件内容永不写日志、永不落 config.json；历史仅存元数据（工具名/时间/长度），输入预览默认关闭
- 所有计算在本地完成，无任何网络请求
- AES-GCM/ChaCha20-Poly1305 输出 = ciphertext‖tag（与 WebCrypto/OpenSSL 约定一致）
- DES/RC4/ECB 已标注安全警示，仅作兼容与教学用途
- 大文件（>200MB）超出当前版本上限

## 版本信息

- v1.0.0：V1.0 全量功能（编码/哈希/对称/经典/压缩互转/生成器/智能识别/历史收藏）

---

## ⚠️ Disclaimer

- **"AS IS"**: This software is provided "AS IS", without any express or implied warranty, including but not limited to merchantability, fitness for a particular purpose, and non-infringement.
- **Use at Your Own Risk**: The developer shall not be liable for any direct or indirect losses (including but not limited to data loss, system damage, business interruption) caused by the use of this software. Users must assess and bear all risks.
- **Data Backup**: It is recommended to back up important data before using this software to prevent irreversible loss.
- **Compatibility Risks**: This software may have unknown defects or be incompatible with certain system environments, hardware configurations, or third-party software. The developer does not guarantee normal operation in all environments.
- **Plugin Disclaimer**: Plugins in this application are independent modules. The developer makes no guarantee regarding the behavior, security, or stability of third-party plugins. Users must assess and bear the risks of using third-party plugins.

> Downloading or using this software indicates that you have read and agree to the above disclaimer.
