---
title: 第三方 SDK 声明
version: 1.1.0
updated: 2026-09-12
language: zh-CN
---

# 第三方 SDK 声明

本文档列出随 **My Desktop Tools** 一起分发的第三方 SDK 及其许可条款。

## Everything SDK（Everything64.dll）

- **厂商**：voidtools（<https://www.voidtools.com/>）
- **SDK 页面**：<https://www.voidtools.com/support/everything/sdk/>
- **组件**：`Everything64.dll`（IPC 客户端库，原样分发，未做任何修改）
- **许可**：voidtools 许可证（<https://www.voidtools.com/License.txt>）——MIT 许可，
  允许商业使用与再分发（含二进制再分发），唯一义务是保留下方版权与许可声明。

### 版权与许可声明

以下为 voidtools 官方 License.txt（<https://www.voidtools.com/License.txt>）现行文本
（2026-09 核对），PCRE 部分为 BSD 风格许可，同样允许再分发：

```text
Everything

Copyright (C) 2018 David Carpenter

Permission is hereby granted, free of charge, to any person obtaining a
copy of this software and associated documentation files (the "Software"),
to deal in the Software without restriction, including without limitation
the rights to use, copy, modify, merge, publish, distribute, sublicense,
and/or sell copies of the Software, and to permit persons to whom the
Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING
FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER
DEALINGS IN THE SOFTWARE.
```

> 许可以 voidtools 官方发布版本（<https://www.voidtools.com/License.txt>）为准。
> 若本副本与在线版本不一致，以在线版本为准。

### 说明

- Everything **客户端本体不随本产品打包分发**。v1.6 起，用户可在设置页一键引导下载：
  应用直连 voidtools 官方源下载安装包（清单经 Gitee/GitHub 双源提供版本号与官方
  SHA-256，下载前强制校验官方域），随后拉起**官方原版安装器**由用户完成安装；
  本产品不镜像、不修改、不转售安装包。
- 本产品仅通过 SDK 向本机运行的 Everything 进程发送搜索查询（IPC 本地通信），
  不会向 voidtools 或任何第三方发送用户数据；「检查更新」与下载均为用户主动触发，
  不做后台轮询。
