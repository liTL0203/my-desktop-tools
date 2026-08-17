---
title: 第三方 SDK 声明
version: 1.0.0
updated: 2026-08-15
language: zh-CN
---

# 第三方 SDK 声明

本文档列出随 **My Desktop Tools** 一起分发的第三方 SDK 及其许可条款。

## Everything SDK（Everything64.dll）

- **厂商**：voidtools（<https://www.voidtools.com/>）
- **SDK 页面**：<https://www.voidtools.com/support/everything/sdk/>
- **组件**：`Everything64.dll`（IPC 客户端库，原样分发，未做任何修改）
- **许可**：voidtools 许可证（<https://www.voidtools.com/License.txt>）——MIT 风格许可，
  允许商业使用与再分发（含二进制再分发），唯一义务是保留下方版权声明。

### 版权声明

```text
Everything software license agreement

voidtools (C) 2026

This software and associated documentation files (the "Software") may only be used in
original unaltered form.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED,
INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A
PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT
HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION
OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE
SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
```

> 许可以 voidtools 官方发布版本（<https://www.voidtools.com/License.txt>）为准。
> 若本副本与在线版本不一致，以在线版本为准。

### 说明

- Everything **客户端本体不随本产品分发**。用户如需启用「Everything 全盘搜索」联动，
  可自行从官网下载并安装 Everything。
- 本产品仅通过 SDK 向本机运行的 Everything 进程发送搜索查询（IPC 本地通信），
  不会向 voidtools 或任何第三方发送用户数据。
