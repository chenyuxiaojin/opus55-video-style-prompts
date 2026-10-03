# 15 种视频风格 · 与内容无关的提示词图鉴

👉 **在线图鉴(带截图、一键复制):打开仓库里的 `index.html`,或看 GitHub Pages。**

样片来自 [@VincentWei93 的展示视频](https://x.com/VincentWei93/status/2104957548797604116),15 种风格全部由 Claude Opus 5.5 写代码制作。本仓库把每种风格交给一个独立 AI 子 agent 逐帧观察,只提取配色、形状、材质、排版、动效节奏、实现手法等**与具体内容无关**的部分,写成可直接复用的提示词(中 / 英)。

| # | 风格 | English | 一句话 |
|---|---|---|---|
| 01 | [逐帧手绘](prompts/01-frame-by-frame-hand-drawn.md) | Frame-by-Frame Hand-Drawn | 纸上线条在沸腾,一拍二的卡通手作温度 |
| 02 | [等轴 2.5D 微缩沙盘](prompts/02-isometric-2.5d-diorama.md) | Isometric 2.5D Diorama | 正交俯视的桌面微缩沙盘,一格格长出、先白后彩 |
| 03 | [扁平矢量](prompts/03-flat-vector.md) | Flat Vector | 纯色几何满屏回弹,一颗珊瑚圆点串起全片 |
| 04 | [线条动画(一笔画)](prompts/04-line-art-(one-continuous-line).md) | Line Art (One Continuous Line) | 一根发光金线不断笔,在深蓝夜幕上从一点长成全景 |
| 05 | [3D 渲染·软糯物理](prompts/05-3d-render-—-soft-physics.md) | 3D Render — Soft Physics | 糖果色充气字砸进胶囊地毯，软糯又有分量 |
| 06 | [形变动画](prompts/06-shape-morph.md) | Shape Morph | 一个形状连续变身讲完整个故事,色块大胆、扁平如剪纸 |
| 07 | [贴纸风科普](prompts/07-sticker-explainer.md) | Sticker Explainer | 白边贴纸拆解硬知识,一镜推过超长信息长图 |
| 08 | [赛博朋克 HUD](prompts/08-cyberpunk-hud---fui.md) | Cyberpunk HUD / FUI | 电影级科幻界面：开机、扫描、锁定，冷青翻琥珀 |
| 09 | [拼贴剪贴](prompts/09-collage-·-cut-out.md) | Collage · Cut-out | 牛皮纸上剪报网点拼贴,12fps 手工步进逐层贴满 |
| 10 | [弥散渐变玻璃拟态](prompts/10-aurora-glassmorphism.md) | Aurora Glassmorphism | 极光雾里浮起磨砂玻璃,一滴液态透镜收成品牌符号 |
| 11 | [几何构成包豪斯](prompts/11-geometric-constructivist-bauhaus.md) | Geometric Constructivist Bauhaus | 原色基本形踩着节拍,在网格上一拍一拍搭成海报 |
| 12 | [复古 Synthwave](prompts/12-retro-synthwave-(80s-neon-vhs).md) | Retro Synthwave (80s Neon VHS) | 霓虹网格奔向条纹落日,铬金大字砸在一盘老录像带上 |
| 13 | [像素风](prompts/13-16-bit-pixel-art.md) | 16-bit Pixel Art | 320×180 低分屏里过完一整天,16 位游戏机开机即冒险 |
| 14 | [液态流动](prompts/14-liquid-motion.md) | Liquid Motion | 糖果色果冻液滴在暗紫镜面上坠落、融合、成字 |
| 15 | [综艺花字](prompts/15-variety-show-captions.md) | Variety Show Captions | 多层描边糖果花字砸上真实素材,把情绪放大十倍 |

## 用法
复制 `prompts/` 里对应风格的提示词 → 贴给 Claude Code 等编程 agent → 把 `{主题}` 等占位符换成你自己的内容。

## 版权说明
截图版权归原视频作者,仅作风格研究引用;提示词为观察后重新撰写。
