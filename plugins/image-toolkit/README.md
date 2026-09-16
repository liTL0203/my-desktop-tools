# 图片工具箱（image-toolkit）

本地图片处理工具箱：格式转换、精确压缩、裁剪旋转、证件照换底色、局部打码、长图拼接、文字/图片水印、EXIF 隐私清理。**全部处理在本机完成，图片不上传任何服务器。**

## 功能介绍

### 格式转换与压缩
- 支持 JPEG / PNG / WebP / BMP / ICO 五种导出格式（ICO 自动生成 16-256 六个尺寸层）
- JPEG 质量压缩：1-100 质量滑块，实时预估输出体积
- **目标体积压缩**：输入目标 KB 数，自动二分搜索输出「不超过目标的最大质量」结果（如压到 200KB 以内）

### 尺寸调整与裁剪
- 百分比 / 精确像素缩放（含微信表情 240、头像 512、1080p/2K/4K 预设）
- 自由裁剪与 1:1 / 4:3 / 16:9 等比例锁定裁剪（画布拖框交互）
- 圆角矩形 / 圆形裁剪（头像场景）

### 旋转与校直
- 90° 旋转（Ctrl+[ / Ctrl+]）、水平 / 垂直翻转
- ±45° 任意角度校直（0.1° 步进），自动裁剪透明边缘

### 换底色（招牌功能）
- 纯色背景自动检测 + 边缘泛洪移除（保护前景内部同色区域，白衬衫不被误删）
- 容差 0-100、边缘羽化 0-5px 精细调节，手动取色采样
- 替换为白 / 红 / 蓝 / 自定义色，或保留透明底（PNG/WebP）

### 证件照套件
- 内置一寸 / 二寸 / 小二寸 / 护照等规格（300dpi），支持自定义规格并保存预设
- 一键出片：背景移除 → 底色替换 → 规格裁剪 → 重采样，单次完成
- 六寸相纸排版（1800×1200，自动铺排一寸 10 张 / 二寸 6 张）

### 局部打码
- 画布拖框选择区域，马赛克（块 4-64px）或高斯模糊（半径 1-50px）
- 多区域管理，每区域独立选择效果

### 拼接与水印
- 长图拼接（纵向/横向，间距可调，宽度自动归一到最窄图）
- 文字水印（字号/颜色/不透明度/旋转，平铺或九宫格定位）
- 图片水印（从队列选择，透明通道正确合成）

### 隐私
- EXIF 信息查看（相机 / 时间 / 焦距 / GPS 定位）
- 所有导出均为重新编码，EXIF（含 GPS）不会带入输出文件

## 使用说明

1. **导入**：点击「导入图片」或直接拖拽图片到窗口（支持 JPG/PNG/WebP/BMP/GIF/TIFF/ICO，单张 ≤ 100MB，队列 ≤ 100 张）
2. **编辑**：右侧面板选择功能 Tab，参数调整实时预览；Ctrl+Z / Ctrl+Y 撤销重做
3. **导出**：点击「应用并预览结果」→ 结果抽屉点「保存到…」选择位置；批量结果可一键全部保存到文件夹

## 注意事项

- 图片全程本地处理，无任何网络行为
- WebP 导出为无损编码；需要压体积请使用 JPEG 目标体积模式
- 带透明通道的图导出 JPEG 时自动白底填充（可在转换面板自定义填充色）
- 手机照片的 EXIF 方向会自动校正（所见即所得）

## 版本信息

- v1.2.0：首个完整版本（V1.0 核心管线 + V1.1 证件照/打码 + V1.2 拼接/水印/EXIF/形状裁剪）

---

## ⚠️ Disclaimer

- **"AS IS"**: This software is provided "AS IS", without any express or implied warranty, including but not limited to merchantability, fitness for a particular purpose, and non-infringement.
- **Use at Your Own Risk**: The developer shall not be liable for any direct or indirect losses (including but not limited to data loss, system damage, business interruption) caused by the use of this software. Users must assess and bear all risks.
- **Data Backup**: It is recommended to back up important data before using this software to prevent irreversible loss.
- **Compatibility Risks**: This software may have unknown defects or be incompatible with certain system environments, hardware configurations, or third-party software. The developer does not guarantee normal operation in all environments.
- **Plugin Disclaimer**: Plugins in this application are independent modules. The developer makes no guarantee regarding the behavior, security, or stability of third-party plugins. Users must assess and bear the risks of using third-party plugins.

> Downloading or using this software indicates that you have read and agree to the above disclaimer.
