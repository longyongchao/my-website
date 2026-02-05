# 近况卡片背景图片

此目录用于存放 `updates.md` 中配置的图片。

## 配置方式

在 `content/updates.md` 的 timeline 项中添加 `images` 数组：

```toml
[[timeline]]
date = "2026-02"
title = "独作论文收录于 ICLR 2026"
description = "..."
tags = ["论文", "ICLR", "深度学习"]
images = ["/images/iclr-logo.jpg", "/images/singapore-landmark.jpg"]
image_fit = "contain"  # 可选：contain 或 cover（默认）
```

## image_fit 参数说明（重要！）

为了解决图片被拉伸/裁剪的问题，新增了 `image_fit` 参数：

### `image_fit = "contain"`（推荐用于 Logo/Icon）

- ✅ **完整显示图片**，不裁剪任何部分
- 图片居中显示，占卡片 70-85% 区域
- 添加阴影效果增加层次感
- 悬浮时轻微放大（1.0 → 1.08）
- **适合**：Logo、Icon、图标、示意图、徽章

```toml
[[timeline]]
title = "加入百度"
images = ["https://upload.wikimedia.org/wikipedia/en/f/f4/Baidu_logo.svg"]
image_fit = "contain"  # Logo 完整显示
```

### `image_fit = "cover"`（默认，推荐用于照片）

- 图片**填满整个卡片**，可能裁剪边缘
- 悬浮时放大 + 视差偏移效果
- **适合**：风景照、会议现场、背景图、人物照片

```toml
[[timeline]]
title = "ICLR 2026"
images = ["/images/conference-hall.jpg"]
# image_fit 不填，默认就是 cover
```

### 双图模式的特殊处理

| 组合 | 效果 |
|-----|-----|
| `contain` 单图 | 居中显示，带阴影 |
| `contain` 双图 | **左右并排**显示两个图标 |
| `cover` 单图 | 全屏背景，视差效果 |
| `cover` 双图 | **对角线分割**两张背景图 |

## 支持图片源

### 1. 本地图片（推荐）
将图片放入 `static/images/` 目录：
```toml
images = ["/images/my-photo.jpg"]
image_fit = "contain"
```

### 2. 网络图片 URL
支持任意 HTTPS 图片链接：
```toml
# Logo 类 - 使用 contain
images = ["https://iclr.cc/static/images/logo.png"]
image_fit = "contain"

# 照片类 - 使用 cover（默认）
images = ["https://images.unsplash.com/photo-xxx/singapore.jpg"]
```

**⚠️ 使用网络图片注意事项：**
| 问题 | 说明 | 解决方案 |
|-----|-----|---------|
| CORS 跨域 | 部分网站禁止外链引用 | 使用允许外链的图床（Unsplash、Wikimedia）|
| HTTPS 强制 | HTTP 链接会被浏览器阻止 | 确保使用 `https://` 协议 |
| 加载速度 | 外部依赖可能影响首屏 | 已默认开启懒加载 |
| 链接失效 | 外链可能变更或删除 | 重要图片下载到本地 |

## 图片建议规格

### Logo/Icon 类（`image_fit = "contain"`）
| 参数 | 建议值 |
|-----|-------|
| 尺寸 | 400×400px 或更高 |
| 比例 | 1:1（正方形）最佳 |
| 格式 | PNG（支持透明背景）或 SVG |
| 背景 | **透明**或纯色 |
| 大小 | < 100KB |

### 照片类（`image_fit = "cover"`）
| 参数 | 建议值 |
|-----|-------|
| 尺寸 | 800×400px 或更高 |
| 比例 | 2:1 或 16:9 |
| 格式 | JPG |
| 大小 | < 200KB |
| 风格 | 深色或低饱和度 |

## 文字可读性保障

无论使用哪种模式，系统都会自动保护文字可读性：

1. **全局渐变遮罩** - 左侧深到右侧浅
2. **文字阴影增强** - 白色文字带深色阴影
3. **标签毛玻璃效果** - `backdrop-filter: blur`
4. **日期徽章悬浮反色** - 突出显示

## 推荐图片来源

| 来源 | 网址 | 适合类型 | 特点 |
|-----|-----|---------|-----|
| **Wikimedia Commons** | commons.wikimedia.org | Logo、标志 | 官方 Logo，SVG 格式，高清 |
| **Unsplash** | unsplash.com | 风景、背景 | 免费高质量摄影，允许外链 |
| **Iconify** | iconify.design | Icon、SVG | 开源图标库 |
| **Simple Icons** | simpleicons.org | 品牌 Logo | 单色 SVG 图标 |
| 本地拍摄 | - | 个人照片 | 完全可控，推荐 |

## 使用示例

### 示例 1：公司实习（Logo）
```toml
[[timeline]]
date = "2025-01"
title = "加入百度大模型算法组"
images = ["https://upload.wikimedia.org/wikipedia/en/f/f4/Baidu_logo.svg"]
image_fit = "contain"  # Logo 完整显示
tags = ["实习", "大模型"]
```

### 示例 2：论文收录（Logo + 地标）
```toml
[[timeline]]
date = "2026-02"
title = "论文收录于 ICLR 2026"
images = [
  "https://iclr.cc/static/images/logo.png",  # 会议 Logo
  "https://images.unsplash.com/photo-xxx/marina-bay.jpg"  # 新加坡地标
]
image_fit = "contain"  # 两张都完整显示，左右并排
tags = ["论文", "ICLR"]
```

### 示例 3：获奖荣誉（照片背景）
```toml
[[timeline]]
date = "2025-06"
title = "获得 XX 奖学金"
images = ["/images/award-ceremony.jpg"]
# image_fit 不填 = cover，照片填满背景
tags = ["荣誉", "奖学金"]
```

### 示例 4：混合模式（Icon + 背景）
```toml
[[timeline]]
date = "2025-08"
title = "开源项目 Star 破千"
images = [
  "/images/project-icon.png",      # 第一张：contain
  "/images/github-screenshot.jpg"  # 第二张：cover（如果支持单独设置）
]
# 目前两张使用相同的 image_fit
image_fit = "contain"
tags = ["开源", "项目"]
```

## 故障排查

### Q: 图片显示不完整，只显示一部分？
**A:** 你可能是用 `cover` 模式显示 Logo。请添加 `image_fit = "contain"`：
```toml
images = ["/images/logo.png"]
image_fit = "contain"
```

### Q: 图片周围有白边/空白太多？
**A:** Logo 类图片建议使用透明背景的 PNG，或者改用 `cover` 模式：
```toml
images = ["/images/photo.jpg"]
image_fit = "cover"  # 填满卡片
```

### Q: 网络图片加载不出来？
**A:** 检查以下几点：
1. 链接是否是 `https://`
2. 直接在浏览器打开链接能否访问
3. 网站是否禁止跨域（CORS）
4. 尝试下载到本地使用

### Q: 双图模式下两张图片重叠？
**A:** 这是 `cover` 模式的对角线分割效果。如需并排显示，改用 `contain`：
```toml
images = ["/images/a.png", "/images/b.png"]
image_fit = "contain"  # 左右并排显示
```

## 当前配置

- `baidu-logo.jpg` - 百度 Logo（contain 模式）
- `iclr-logo.jpg` - ICLR 会议 Logo（contain 模式）
- `singapore-landmark.jpg` - 新加坡地标（contain 模式）

请将实际图片放入此目录，或直接在配置中使用网络链接。
