+++
title = "近况"
subtitle = "记录人生中的重要里程碑"
layout = "updates"

[[timeline]]
date = "2025-01"
title = "加入百度大模型算法组"
description = "以实习生身份加入百度大模型算法组，参与前沿大语言模型的研究与开发工作。专注于模型优化与算法创新，致力于推动 AI 技术的边界。"
tags = ["实习", "大模型", "算法"]
# Logo/Icon 类图片使用 contain 模式，完整显示
images = ["/images/baidu-logo.jpg"]
image_fit = "cover"

[[timeline]]
date = "2026-02"
title = "🎉独作论文收录于 ICLR 2026"
description = "我的独立研究论文被国际顶级会议 ICLR 2026 接收。这项研究探索了深度学习领域的新方向，为领域发展贡献了自己的一份力量。"
tags = ["论文", "ICLR", "深度学习"]
# 照片/背景图使用 cover 模式（或不填，默认就是 cover）
images = ["/images/iclr-logo.jpg", "/images/rio-de-janeiro-landmark.jpg"]
image_fit = "contain"
# 外部链接（可选）
github = "https://github.com/yourusername/iclr-2026-paper"
arxiv = "https://arxiv.org/abs/2501.xxxxx"
huggingface = "https://huggingface.co/yourusername/iclr-2026-model"
+++

> 时间是最好的见证者，每一步都值得被记录。

<!-- 
图片配置说明：
================================================================================

【基础配置】
在 timeline 项中添加 images 数组，支持 1-2 张图片：

  images = ["/images/xxx.jpg"]           # 单张图片
  images = ["/images/a.jpg", "/images/b.jpg"]  # 两张图片

【图片适配模式 - image_fit 参数】

1. contain（推荐用于 Logo/Icon）
   - 完整显示图片，不裁剪
   - 图片会居中显示，留有一定边距
   - 悬浮时有轻微放大和阴影效果
   - 适合：Logo、Icon、图标、示意图
   
   示例：
   images = ["https://example.com/logo.png"]
   image_fit = "contain"

2. cover（默认，推荐用于照片/背景）
   - 填满整个卡片，可能裁剪边缘
   - 悬浮时图片放大+视差偏移
   - 适合：风景照、会议现场、背景图
   
   示例：
   images = ["/images/photo.jpg"]
   # image_fit 不填，默认就是 cover

【图片源类型】

1. 本地图片（推荐）
   将图片放入 static/images/ 目录，使用根路径引用：
   images = ["/images/photo.jpg"]

2. 网络图片 URL（支持 HTTPS）
   images = ["https://example.com/logo.png"]
   
   ⚠️ 注意事项：
   - 确保图片允许跨域访问（CORS）
   - 使用 HTTPS 避免混合内容警告
   - 外链可能失效，重要图片建议本地备份

【双图组合建议】
- contain + contain：左右并排显示两个 Logo
- cover + cover：对角线分割，两张背景图
- contain + cover：左图标 + 右背景（视觉效果丰富）

【推荐图片规格】
- Logo/Icon：400x400px 以上，透明背景 PNG 最佳
- 照片：800x400px 或更高，2:1 或 16:9 比例
- 大小：单张 < 200KB
- 风格：深色/低饱和度，与文字对比适中

【链接配置 - 可选】
支持以下外部链接，会在卡片底部显示对应图标按钮：

  github = "https://github.com/username/repo"
  arxiv = "https://arxiv.org/abs/2501.xxxxx"
  huggingface = "https://huggingface.co/username/model"
  paper = "https://openreview.net/forum?id=xxxxx"
  website = "https://your-project-website.com"

  支持的链接类型：github, arxiv, huggingface, paper, website

【自定义图标链接 - 可选】
使用 Iconify 图标库中的任意图标：

  [[timeline.icons]]
  icon = "simple-icons:google-scholar"
  url = "https://scholar.google.com/citations?user=xxxxx"
  title = "Google Scholar"

  [[timeline.icons]]
  icon = "mdi:twitter"
  url = "https://twitter.com/yourusername"
  title = "Twitter"

  格式说明：
  - icon: Iconify 图标名称，格式为 "图标集:图标名"
  - url: 链接地址
  - title: 鼠标悬浮时显示的提示文字
================================================================================
-->
