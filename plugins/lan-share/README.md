# 就近快传

同一网络内的电脑之间互传文件、文件夹和文字——不压缩、不中转、不上传云端。配对一次即成信任设备，之后自动接收；传输中断自动保存进度，对方上线后从断点继续。

- **功能**

- **附近设备自动发现**：打开聊天页自动扫描，附近设备出现在左侧列表（未配对的点击即配对）；也可按地址手动添加；手机/浏览器扫码入口也在聊天页侧栏
- **六位码配对**：首次连接两侧屏幕显示同源配对码，码一致即确认对方身份；配对后成为信任设备
- **文件与文件夹直传**：拖入即发（保持目录结构），可同时发给多台设备
- **断点续传**：传输中断（断网、对方关机）后进度保留，重连自动从断点继续，跨重启有效
- **远程浏览**：浏览对方「共享目录」里的文件，勾选需要的拉回本机；全程只读
- **浏览器收发**：手机或同事电脑扫码打开网页（无需安装），输入配对码即可互传（配对码可在设置中固定为常用六位数字）；配对状态在刷新后保持，与电脑双向聊天：文字气泡、文件收发都在同一条时间线（点 + 或整卡拖入即可回传任意文件，带实时进度；收到的文件一键下载）；消息时间精确到秒；浏览器可给自己起设备名，多台设备在电脑端一目了然
- **剪贴板同步**：与信任设备互相同步文字与链接；验证码等敏感内容自动掩码且不外发
- **点对点加密**：设备间传输内容加密，密钥仅存双方本机
- **聊天式会话**：微信式统一交互——每个设备一个会话，发文字、传文件、收文件、传输进度全部在同一条时间线里；Enter 发消息，点 + 或拖入发文件
- **传输管理**：进度、速度、暂停/取消、历史与统计
- **网络诊断**：发现不到设备时一键排查（防火墙、网络隔离等建议）

## 使用方法

1. 两台电脑都安装本工具并打开「就近快传」（或对端用浏览器打开本机展示的地址）
2. 在设备页点击未配对设备的「发送」开始配对：核对两侧六位码一致后双方确认
3. 拖入文件即发送；接收方可设为「每次询问 / 信任设备自动 / 全部自动」
4. 想取文件：设备页点「浏览」→ 勾选 → 拉取到本机（需对方在设置中添加共享目录）
5. 手机互传：设备页打开「浏览器收发」，扫码输码即用

## 无浏览器环境（Linux 服务器等）可用命令行

对方没有图形界面时，用 curl 同样可以互传（地址和配对码在电脑端顶部横幅查看）：

```bash
# 1. 配对换取会话令牌
TOKEN=$(curl -s -X POST -H "Content-Type: application/json"   -d '{"code":"配对码"}'   "http://电脑IP:29180/api/webep/pair" | grep -o '"token":"[^"]*' | cut -d'"' -f4)

# 2. 发送文字到电脑
curl -X POST -H "Content-Type: application/json"   -d '{"content":"来自Linux的消息"}'   "http://电脑IP:29180/api/webep/text?token=$TOKEN"

# 3. 上传文件到电脑
curl -X PUT --data-binary @文件名.tar.gz   "http://电脑IP:29180/api/webep/upload?token=$TOKEN&name=文件名.tar.gz&size=$(stat -c%s 文件名.tar.gz)"

# 4. 查看电脑发来的文件（取 boxId）
curl -s "http://电脑IP:29180/api/webep/inbox?token=$TOKEN"

# 5. 下载电脑发来的文件
curl -o 文件名 -L "http://电脑IP:29180/api/webep/file?token=$TOKEN&boxId=上一步的boxId"
```

## Linux 节点（无界面服务器）

随插件附带 `linux-x86_64/lan-share-linux.tar.gz`（musl 静态，无依赖）：

```bash
tar xzf lan-share-linux.tar.gz && cd lan-share-linux
sudo cp lan-share-noded /usr/local/bin/ && sudo cp lan-share.toml /etc/
sudo cp lan-share.service /etc/systemd/system/ && sudo systemctl enable --now lan-share
```

Linux 节点自动出现在 Windows 插件的聊天列表（同套配对/加密/续传），`http://节点IP:29180/admin` 为管理页（toml 中 admin_code 进入，含连接指引）。详见包内 README.md。

## 注意事项

- 两台设备须在同一局域网（同一路由器/交换机）；广播不跨网段，跨网段请手动添加地址
- 首次运行如 Windows 防火墙弹窗，请允许并勾选「专用网络」
- 浏览器收发通道为配对码授权的局域网明文通道（点对点插件间通道为加密传输）
- 传输内容加密仅覆盖插件间通道；文件名等元数据对本网络内抓包可见
- 接收文件默认保存在「下载/就近快传」，可在设置中更改
- 浏览器端上传不支持断点续传（网页即用即走）
- 浏览器配对状态保存在该浏览器本地；清除站点数据或更换浏览器需重新输配对码

## 版本信息

| 版本 | 日期 | 说明 |
|------|------|------|
| 0.1.0 | 2026-09-26 | 首个开发版本：发现/配对加密直传/断点续传/远程浏览/浏览器收发/剪贴板同步/网络诊断 |

---

<details>
<summary>English</summary>

# Swift Drop (lan-share)

Move files, folders and text between PCs on the same network — no compression, no relay, no cloud upload. Pair once to become trusted devices with auto-accept; interrupted transfers keep their progress and resume from the breakpoint when the peer comes back.

## Features

- **Nearby device discovery**: peers appear automatically on the same LAN; manual address fallback
- **6-digit pairing**: both screens show the same derived code — a match proves the identity; paired devices become trusted
- **File & folder transfer**: drag and drop (directory structure preserved), send to multiple devices at once
- **Resume**: progress survives disconnections and restarts, resuming from the exact breakpoint
- **Remote browse**: browse a peer's shared folders and pull only what you need — strictly read-only
- **Browser endpoint**: phones or colleagues' PCs scan a QR code, enter the pairing code, and transfer with zero installation
- **Clipboard sync**: text and links sync between trusted devices; sensitive codes are masked and never pushed
- **Peer-to-peer encryption**: content encrypted between plugins; keys live only on the two machines
- **Transfer management**: progress, speed, pause/cancel, history and stats
- **Network diagnosis**: one-click checks with actionable advice (firewall, AP isolation)

## Usage

1. Open Swift Drop on both PCs (or open the served page in a browser on the other side)
2. Tap "Send" on an unpaired device to start pairing; confirm the matching 6-digit code on both screens
3. Drop files to send; receiving policy: ask every time / auto-accept trusted / auto-accept all
4. To pull files: "Browse" on the Devices page → select → pull (peer must add shared folders in Settings)
5. Phone transfers: enable Browser sharing, scan the QR code, enter the code

## Notes

- Both sides must be on the same LAN; broadcasts do not cross subnets — add the address manually in that case
- Allow the app on Private networks if Windows Firewall prompts on first run
- The browser endpoint is a code-gated plaintext LAN channel (plugin-to-plugin channels are encrypted)
- Encryption covers content between plugins; metadata such as filenames remains visible to sniffers on the same network
- Received files land in "Downloads/就近快传" by default — changeable in Settings
- Browser uploads do not support resume

| Version | Date | Notes |
|---------|------|-------|
| 0.1.0 | 2026-09-26 | Initial dev release: discovery, encrypted pairing, resumable transfer, remote browse, browser endpoint, clipboard sync, network diagnosis |

</details>

---

## ⚠️ Disclaimer

- **"AS IS"**: This software is provided "AS IS", without any express or implied warranty, including but not limited to merchantability, fitness for a particular purpose, and non-infringement.
- **Use at Your Own Risk**: The developer shall not be liable for any direct or indirect losses (including but not limited to data loss, system damage, business interruption) caused by the use of this software. Users must assess and bear all risks.
- **Data Backup**: It is recommended to back up important data before using this software to prevent irreversible loss.
- **Compatibility Risks**: This software may have unknown defects or be incompatible with certain system environments, hardware configurations, or third-party software. The developer does not guarantee normal operation in all environments.
- **Plugin Disclaimer**: Plugins in this application are independent modules. The developer makes no guarantee regarding the behavior, security, or stability of third-party plugins. Users must assess and bear the risks of using third-party plugins.

> Downloading or using this software indicates that you have read and agree to the above disclaimer.
