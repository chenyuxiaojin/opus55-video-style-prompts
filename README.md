# 15 种视频风格 · 与内容无关的提示词图鉴

👉 **在线图鉴(带截图、一键复制):https://chenyuxiaojin.github.io/opus55-video-style-prompts/**

样片来自 [@VincentWei93 的展示视频](https://x.com/VincentWei93/status/2104957548797604116),15 种风格全部由 Claude Opus 5.5 写代码制作。本仓库把每种风格(10 秒、约 300 帧)交给一个独立 AI 子 agent 逐帧全部过目,剥离样片讲的具体内容,只留配色、形状、材质、排版、动效节奏、实现手法等**技巧层**,写成尽量精简、可直接复用的提示词(中 / 英)。

| # | 风格 | English | 一句话 |
|---|---|---|---|
| 01 | [逐帧手绘](prompts/01-frame-by-frame-hand-drawn.md) | Frame-by-Frame Hand-Drawn | 一拍二线条沸腾,纸上的手温 |
| 02 | [等轴2.5D](prompts/02-isometric-2.5d.md) | Isometric 2.5D | 桌面微缩模型,一格一格自己长出来 |
| 03 | [扁平矢量](prompts/03-flat-vector.md) | Flat Vector | 纯色几何零阴影,一颗圆点弹出全片节奏 |
| 04 | [线条动画](prompts/04-single-line-art.md) | Single-Line Art | 一根金线不离纸,留白即画面 |
| 05 | [3D渲染](prompts/05-3d-render.md) | 3D Render | 粉彩充气质感,软糯落地有分量 |
| 06 | [形变动画](prompts/06-shape-morph.md) | Shape Morph | 一个形状连续变身,底色随形翻页 |
| 07 | [贴纸风科普](prompts/07-sticker-explainer.md) | Sticker Explainer | 白描边贴纸,一镜推到底的长画布科普 |
| 08 | [赛博朋克HUD](prompts/08-cyberpunk-hud-(fui).md) | Cyberpunk HUD (FUI) | 暗底青光细线界面,高潮一瞬转琥珀 |
| 09 | [拼贴剪贴](prompts/09-collage-cut-out.md) | Collage Cut-Out | 剪报网点纸片,12帧逐格拍上 |
| 10 | [弥散渐变玻璃拟态](prompts/10-aurora-glassmorphism.md) | Aurora Glassmorphism | 极光暗场上浮磨砂玻璃,液态透镜折光 |
| 11 | [几何构成包豪斯](prompts/11-geometric-bauhaus-construction.md) | Geometric Bauhaus Construction | 三原色几何块踩着节拍在网格上搭建 |
| 12 | [复古Synthwave](prompts/12-retro-synthwave-vhs.md) | Retro Synthwave VHS | 霓虹网格落日,录像带回放 |
| 13 | [像素风](prompts/13-16-bit-pixel-art.md) | 16-bit Pixel Art | 低分辨率逐点画,CRT 里的日夜换色 |
| 14 | [液态流动](prompts/14-liquid-motion.md) | Liquid Motion | 果冻般可捏的液体,粘连拉丝融合弹跳 |
| 15 | [综艺花字](prompts/15-variety-show-captions.md) | Variety Show Captions | 多层描边弹跳花字,按情绪放大笑点 |

## 用法
复制 `prompts/` 里对应风格的提示词 → 贴给 Claude Code 等编程 agent → 把最后一行 `{在这里写你的内容}` 换成你自己的内容。

## 版权说明
截图版权归原视频作者,仅作风格研究引用;提示词为观察后重新撰写。
