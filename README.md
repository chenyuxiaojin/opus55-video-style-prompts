# 15 种视频风格 · 与内容无关的提示词图鉴

👉 **在线图鉴(一键复制、看逐帧证据):https://chenyuxiaojin.github.io/opus55-video-style-prompts/**

样片来自 [@VincentWei93 的展示视频](https://x.com/VincentWei93/status/2104957548797604116),15 种风格全部由 Claude Opus 5.5 写代码制作。本仓库把每种风格(10 秒、约 300 帧)交给一个独立 AI 子 agent 逐帧全部过目,剥离样片讲的具体内容,只留配色、形状、材质、排版、动效节奏、实现手法等**技巧层**,写成尽量精简、可直接复用的提示词(中 / 英)。

**用法**:复制下面任一风格的提示词 → 贴给 Claude Code 等编程 agent → 把最后一行 `{在这里写你的内容}` 换成你自己的内容。

<table><tr><td align=center><a href="prompts/01-frame-by-frame-hand-drawn.md"><img src="images/01-1.webp" width="170"><br>01 逐帧手绘</a></td><td align=center><a href="prompts/02-isometric-2.5d.md"><img src="images/02-1.webp" width="170"><br>02 等轴2.5D</a></td><td align=center><a href="prompts/03-flat-vector.md"><img src="images/03-1.webp" width="170"><br>03 扁平矢量</a></td><td align=center><a href="prompts/04-single-line-art.md"><img src="images/04-1.webp" width="170"><br>04 线条动画</a></td><td align=center><a href="prompts/05-3d-render.md"><img src="images/05-1.webp" width="170"><br>05 3D渲染</a></td></tr><tr><td align=center><a href="prompts/06-shape-morph.md"><img src="images/06-1.webp" width="170"><br>06 形变动画</a></td><td align=center><a href="prompts/07-sticker-explainer.md"><img src="images/07-1.webp" width="170"><br>07 贴纸风科普</a></td><td align=center><a href="prompts/08-cyberpunk-hud-(fui).md"><img src="images/08-1.webp" width="170"><br>08 赛博朋克HUD</a></td><td align=center><a href="prompts/09-collage-cut-out.md"><img src="images/09-1.webp" width="170"><br>09 拼贴剪贴</a></td><td align=center><a href="prompts/10-aurora-glassmorphism.md"><img src="images/10-1.webp" width="170"><br>10 弥散渐变玻璃拟态</a></td></tr><tr><td align=center><a href="prompts/11-geometric-bauhaus-construction.md"><img src="images/11-1.webp" width="170"><br>11 几何构成包豪斯</a></td><td align=center><a href="prompts/12-retro-synthwave-vhs.md"><img src="images/12-1.webp" width="170"><br>12 复古Synthwave</a></td><td align=center><a href="prompts/13-16-bit-pixel-art.md"><img src="images/13-1.webp" width="170"><br>13 像素风</a></td><td align=center><a href="prompts/14-liquid-motion.md"><img src="images/14-1.webp" width="170"><br>14 液态流动</a></td><td align=center><a href="prompts/15-variety-show-captions.md"><img src="images/15-1.webp" width="170"><br>15 综艺花字</a></td></tr></table>

## 01 · 逐帧手绘 <sub>Frame-by-Frame Hand-Drawn</sub>

> 一拍二线条沸腾,纸上的手温

<img src="images/01-1.webp" width="32%"> <img src="images/01-2.webp" width="32%"> <img src="images/01-3.webp" width="32%">

```text
风格:逐帧手绘,线条沸腾。
画面:纸纹米底#EEE1BE;红#D33631黄#F2C429平涂,墨黑#1D1512粗描边;主体后柔光晕#ECDA98;排线阴影。
字体:如需文字:圆胖手写粗体逐笔写出。
动效:默认on 2s,快动作on 1s,定格on 3s;每张新图线抖±2px;挤压拉伸、残影、速度线;高潮插1-2帧满屏星爆冲击;景别硬切不推拉。
实现:Canvas笔刷;以floor(frame/step)为种子抖路径与线宽,位置按step取整。
不要:丝滑缓动;矢量死线;渐变;定格内乱抖。
内容:{在这里写你的内容}
```

<details><summary>English prompt</summary>

```text
Style: frame-by-frame hand-drawn cartoon, boiling lines.
Look: grainy cream paper #EEE1BE; flat red #D33631 and yellow #F2C429 fills, thick ink #1D1512 outlines, soft glow #ECDA98 behind the subject; hatched shadows.
Type: if text is needed: chunky rounded hand-lettering written on stroke by stroke.
Motion: on 2s by default, fast actions on 1s, holds on 3s; each new drawing jitters lines ±2px; squash & stretch, smears, speed lines; climax gets 1-2 full-screen starburst impact frames; hard cuts between shot sizes, no zooms.
Build: Canvas brush; floor(frame/step) seeds path and stroke-width jitter; positions quantized to the step.
Avoid: silky easing; dead vector lines; gradients; jitter within one held drawing.
Content: {your content here}
```

</details>

## 02 · 等轴2.5D <sub>Isometric 2.5D</sub>

> 桌面微缩模型,一格一格自己长出来

<img src="images/02-1.webp" width="32%"> <img src="images/02-2.webp" width="32%"> <img src="images/02-3.webp" width="32%">

```text
风格:等轴2.5D桌面微缩模型,逐格自己长出来
画面:正交等轴无透视;万物落在方格地块+厚底座;先素白#EDE8F5配深靛#1B1650,高潮从中心一波上色#A4EDC4/#9F86DF/#62EFF1;圆角块、软阴影
字体:粗圆3D挤出字平贴地面;等宽小字注释;白底数据卡+引线
动效:30fps连续带运动模糊,相机慢漂。地块由中心逐环错峰飞入(2s);物件逐格拔高,先线框后实体,轻过冲(3s);光环脉冲0.5s内上色;末尾拉远,字母逐个弹落
实现:Three.js正交相机+InstancedMesh
不要:透视、写实材质、满屏霓虹、同时出现
内容:{在这里写你的内容}
```

<details><summary>English prompt</summary>

```text
Style: isometric 2.5D tabletop miniature that builds itself tile by tile
Look: orthographic iso, no perspective; everything sits on a tile grid over a thick base slab; start white clay #EDE8F5 with deep indigo #1B1650, then a color wave spreads from center at the climax (mint #A4EDC4 / violet #9F86DF / cyan glow #62EFF1); rounded blocks, soft shadows
Type: chunky rounded 3D-extruded letters lying flat on the ground; small monospace notes; white data cards with leader lines
Motion: continuous 30fps with motion blur, slow camera drift. Tiles fly in ring by ring from center (2s); objects rise per cell, wireframe first then solid, slight overshoot (3s); a ring pulse recolors all within 0.5s; finally pull back, letters drop in one by one with a bounce
Build: Three.js orthographic camera + InstancedMesh
Avoid: perspective, realistic materials, neon everywhere, everything at once
Content: {your content here}
```

</details>

## 03 · 扁平矢量 <sub>Flat Vector</sub>

> 纯色几何零阴影,一颗圆点弹出全片节奏

<img src="images/03-1.webp" width="32%"> <img src="images/03-2.webp" width="32%"> <img src="images/03-3.webp" width="32%">

```text
风格:扁平矢量,纯色几何零阴影,主色圆点贯穿全片。
画面:钴蓝#2B1EF4底,珊瑚#F14B4F主色,薄荷#3DFDA7/明黄#F7CC30点缀,奶油#FDF7E9留白;只用圆、圆角矩形、胶囊。
字体:圆润粗体小写,宽字距副标逐字弹出。
动效:30fps+方向模糊;下落拉伸1.2,落地压扁1.5×0.6停2帧,回弹过冲10%+放射线;错开3帧弹出;每场2秒,0.4秒推镜穿框或圆点扩张擦除换场。
实现:SVG+GSAP,scaleX/Y,clip-path。
不要:投影渐变;匀速;一拍二;超5色。
内容:{在这里写你的内容}
```

<details><summary>English prompt</summary>

```text
Style: flat vector, solid geometry, zero shadows; one accent dot runs through the whole piece.
Look: cobalt #2B1EF4 ground, coral #F14B4F lead, mint #3DFDA7 / yellow #F7CC30 accents, cream #FDF7E9 negative space; only circles, rounded rects, pills.
Type: rounded heavy lowercase; wide-tracked subline, letters pop in one by one.
Motion: 30fps + directional blur; falls stretch 1.2x, lands squash 1.5x0.6 held 2 frames, 10% rebound overshoot with radial tick lines; 3-frame stagger pop-ins; ~2s per beat, change scenes with a 0.4s push-in through a small frame or the dot swelling into a circle wipe.
Build: SVG + GSAP, scaleX/Y, clip-path circle.
Avoid: shadows/gradients; linear easing; on-twos; more than 5 colors on screen.
Content: {your content here}
```

</details>

## 04 · 线条动画 <sub>Single-Line Art</sub>

> 一根金线不离纸,留白即画面

<img src="images/04-1.webp" width="32%"> <img src="images/04-2.webp" width="32%"> <img src="images/04-3.webp" width="32%">

```text
风格:一根金线一笔画到底,大留白
画面:底 #151E2D→#070E16 暗角;线 #C9B27E 2px;笔尖 #FFF8E8 光点;末个闭合形填金 #E4D3A0
字体:如需文字:宽字距细衬线,定版后淡入
动效:30fps 连续;笔尖匀速,拐角停 5 帧;镜头跟笔;新线亮白 1s 退成金;闭合时3帧由外向内填满+光环外扩;再 0.8s 拉远定版
实现:SVG单path+stroke-dashoffset;getPointAtLength 定光点与相机
不要:多条线;断笔;提前填色;快切
内容:{在这里写你的内容}
```

<details><summary>English prompt</summary>

```text
Style: one gold line drawn without lifting, lots of negative space
Look: radial bg #151E2D→#070E16 vignette; line #C9B27E 2–3px round caps; white-hot tip #FFF8E8; only the final closed shape fills gold #E4D3A0
Type: if text is needed: after lockup, wide-tracked thin serif caps centered below, blur-fade in
Motion: smooth 30fps; tip near-constant speed, holds 4–6 frames at corners; camera pans with tip; fresh line glows white, fades to gold over 1s; on closure, 3-frame outside-in fill + expanding glow ring; then 0.8s ease-in-out pull-back to lockup
Build: single SVG path + stroke-dashoffset; getPointAtLength drives tip glow and camera
Avoid: multiple lines; breaks or jumps; early fills; hard cuts or shake
Content: {your content here}
```

</details>

## 05 · 3D渲染 <sub>3D Render</sub>

> 粉彩充气质感,软糯落地有分量

<img src="images/05-1.webp" width="32%"> <img src="images/05-2.webp" width="32%"> <img src="images/05-3.webp" width="32%">

```text
风格:粉彩3D棚拍,充气糖果感,软糯有分量
画面:#E8336F主体/#F0CDBA地/#DDB8D2天/#A48BE8换色;釉面鼓胀;数千小球铺地;柔光、低机位浅景深、远景雾化
字体:主标做充气3D圆胖字;副标极小全大写、宽字距,末淡入
动效:24fps;元素逐个落入隔0.45s,触地压扁20%回弹、压坑;一镜缓推环绕;高潮镜面重物砸入,小球溅飞、自落点波纹换色;末1.5s定版。
实现:Blender Cycles+Python;实例化+刚体;运动模糊。
不要:扁平假3D;黑底霓虹;硬切;匀速。
内容:{在这里写你的内容}
```

<details><summary>English prompt</summary>

```text
Style: pastel 3D studio render, inflated candy-gloss, soft yet weighty.
Look: #E8336F hero / #F0CDBA ground / #DDB8D2 sky / #A48BE8 takeover; glossy puffy forms; ground tiled with thousands of small spheres; soft key light, low camera, shallow DOF, hazy distance.
Type: headline as chubby inflated 3D letters; tiny all-caps subline, wide tracking, fades in last.
Motion: 24fps feel; elements drop in one by one ~0.45s apart, squash ~20% on landing, rebound, dent the ground; one continuous take, slow dolly-orbit; climax: a chrome heavy object slams in, spheres splash, color ripples outward from impact to the takeover hue; hold final 1.5s.
Build: Blender Cycles + Python; instancing + rigid-body sim; motion blur on.
Avoid: flat fake 3D; dark neon; hard cuts; linear motion.
Content: {your content here}
```

</details>

## 06 · 形变动画 <sub>Shape Morph</sub>

> 一个形状连续变身,底色随形翻页

<img src="images/06-1.webp" width="32%"> <img src="images/06-2.webp" width="32%"> <img src="images/06-3.webp" width="32%">

```text
风格:单一形状连续变形串起全片,扁平图标极简。
画面:#F3EFE4 纸白、#15141A 墨黑、#E8422C 红、#F4BF35 黄、#262ED7 钴蓝大色块;居中单主体,实心填充+一道斜向浅色折面;全屏纸纹+轻暗角。
字体:如需文字:粗几何无衬线;角落小号等宽章节号,换段上下滚动替换。
动效:30fps 全帧不抽帧;每形停 1–1.5s,形变 8–12 帧 ease-in-out,落地挤压回弹约 10%;快移带方向模糊;换段时新底色从主体中心以软边圆 5–8 帧加速扩满屏;形内换色用斜向擦除。
实现:flubber 插值 SVG path d;底色 clip-path circle+blur。
不要:交叉淡化换形;多主体并排;线稿描边;渐变光。
内容:{在这里写你的内容}
```

<details><summary>English prompt</summary>

```text
Style: one shape continuously morphs to carry the whole piece; flat, iconic minimalism.
Visual: #F3EFE4 paper white, #15141A ink, #E8422C red, #F4BF35 yellow, #262ED7 cobalt as big flat fields; one centered subject, solid fill plus one diagonal lighter fold facet; full-frame paper grain, light vignette.
Type (if needed): bold geometric sans; small mono chapter index in a corner, rolls vertically on section change.
Motion: 30fps, no stepping; hold each form 1–1.5s, morph in 8–12 frames ease-in-out, ~10% squash-rebound on landing; directional blur on fast moves; on section change the new background grows from the subject's center as a soft-edged circle filling the screen in 5–8 accelerating frames; recolor inside the shape with a diagonal wipe.
Build: flubber-interpolated SVG path d; background via clip-path circle + blur.
Avoid: crossfading between shapes; multiple subjects side by side; outline line-art; gradient glows.
Content: {your content here}
```

</details>

## 07 · 贴纸风科普 <sub>Sticker Explainer</sub>

> 白描边贴纸,一镜推到底的长画布科普

<img src="images/07-1.webp" width="32%"> <img src="images/07-2.webp" width="32%"> <img src="images/07-3.webp" width="32%">

```text
风格:贴纸风科普,一张超长画布,镜头一路推下去。
画面:浅灰点阵底#EAEFF2,墨#26313A,红#EE4A3C点重点,收尾转深底#1F2A31;抠图套粗白描边+软投影;数据用墨色圆角小方块。
字体:粗黑体标题+宽字距英文小副标,关键词下红条划出;角落固定章节进度条。
动效:30fps;换章镜头0.5s急推+强运动模糊;同批方块错峰飞向新布局,旋转落定;元素5帧弹出微过冲;数字滚动。收尾拉远,画布缩进白边容器,关键数字贴纸弹出。
实现:Remotion超高画布+camera;方块同key做FLIP变形;多帧采样运动模糊;SVG feMorphology描边。
不要:硬切/淡入换页;无描边扁平图标;多色;匀速漂移。
内容:{在这里写你的内容}
```

<details><summary>English prompt</summary>

```text
Style: sticker explainer — one extra-tall canvas, the camera keeps pushing down through it.
Look: light gray dot-grid bg #EAEFF2, ink #26313A, red #EE4A3C for emphasis only, finale on dark #1F2A31; cutouts get a thick white sticker outline + soft shadow; data as small rounded ink chips.
Type: heavy sans headlines + wide-tracked small English subtitle; red marker bar wipes under key words; fixed corner chapter progress bar.
Motion: smooth 30fps; chapter change = 0.5s fast camera push with strong directional motion blur; the same chips fly staggered into each new layout and settle with rotation; elements pop in ~5 frames with slight overshoot; numbers count up. Finale pulls back: whole canvas shrinks into a white-outlined container, key number pops out as a sticker.
Build: Remotion tall canvas + camera transform; same-key chips FLIP between layouts; multi-sample motion blur; SVG feMorphology outline.
Avoid: hard cuts/fades between pages; flat outline-less icons; many colors; constant-speed drifting camera.
Content: {your content here}
```

</details>

## 08 · 赛博朋克HUD <sub>Cyberpunk HUD (FUI)</sub>

> 暗底青光细线界面,高潮一瞬转琥珀

<img src="images/08-1.webp" width="32%"> <img src="images/08-2.webp" width="32%"> <img src="images/08-3.webp" width="32%">

```text
风格:科幻FUI发光细线仪表盘。
画面:#03080A底,#2EE6E6主线,#0F4F55暗线,#EAFBFF数字,高潮转#FF9A1F。主体套分段刻度环+准星,两侧数据栏+角括号,蜂窝底纹+辉光。
字体:等宽全大写,小标签配大数字。
动效:30fps连续。CRT开机进、压线成点出(各0.3s);弧段描边,逐行打字;数字乱跳后落定。转折2帧切片+RGB分离;高潮白闪1帧→3帧转琥珀→推镜后硬切回。
实现:Three.js线框+Bloom;SVG描边;种子随机乱码。
不要:无辉光;多色;实心块;圆体字。
内容:{在这里写你的内容}
```

<details><summary>English prompt</summary>

```text
Style: sci-fi film FUI — glowing hairline instrument panels on near-black.
Visual: bg #03080A, lines #2EE6E6, dim #0F4F55, big numerals #EAFBFF, climax shifts to #FF9A1F. Subject wrapped in segmented tick rings + crosshair; side data columns, corner brackets, faint hex grid, bloom.
Type: monospace, uppercase, wide tracking; tiny labels vs big numerals.
Motion: smooth 30fps. CRT power-on in, power-off squeeze-to-dot out (0.3s each); arcs draw on, lines type with cursor; numbers scramble then settle and tick. Beat change: 2-frame slice offset + RGB split. Climax: 1-frame white flash → shockwave → amber in 3 frames → push-in, hard snap back.
Build: Three.js wireframe + bloom pass; SVG stroke draw; seeded-random glyph scramble.
Avoid: no glow; many hues; big solid fills; rounded fonts.
Content: {your content here}
```

</details>

## 09 · 拼贴剪贴 <sub>Collage Cut-Out</sub>

> 剪报网点纸片,12帧逐格拍上

<img src="images/09-1.webp" width="32%"> <img src="images/09-2.webp" width="32%"> <img src="images/09-3.webp" width="32%">

```text
风格:剪报纸片拼贴,逐格跳动。
画面:牛皮纸#8A7258+纸纹暗角;米白#ECE6D6、印刷红#A2131A、墨黑#100F0A。照片转黑白粗网点,抠图留白边+软投影;撕边、胶带。
字体:粗压缩大写;单字纸片红黑白交替各歪±8°。
动效:2/3帧交替保持=12fps。元素拍上140%→97%→100%,4步落定;剪刀沿虚线剪开掀出下层;撕纸卷开转场;约2秒一个高潮。
实现:Remotion时间量化12fps;SVG噪声clipPath撕边;spring。
不要:平滑补间;扁平矢量;干净直边;发光。
内容:{在这里写你的内容}
```

<details><summary>English prompt</summary>

```text
Style: paper collage; everything is a clipped scrap, animated in 12fps steps.
Look: kraft #8A7258 with grain+vignette; cream #ECE6D6, print red #A2131A, ink #100F0A. Photos as coarse B/W halftone with white cut border + soft shadow; torn edges, tape.
Type: heavy condensed caps; ransom-note letter chips alternating red/black/cream, each tilted ±8°.
Motion: alternating 2/3-frame holds at 30fps = 12fps. Items slap on 140%→97%→100% in 4 steps; scissors cut a dashed line, then a paper flap opens to reveal the layer below; paper-tear-and-curl transitions. One big event every ~2s.
Build: Remotion, quantize time to 12fps; SVG-noise clipPath torn edges; overshoot spring.
Avoid: smooth tweening; flat vector art; clean straight edges; glows/gradients.
Content: {your content here}
```

</details>

## 10 · 弥散渐变玻璃拟态 <sub>Aurora Glassmorphism</sub>

> 极光暗场上浮磨砂玻璃,液态透镜折光

<img src="images/10-1.webp" width="32%"> <img src="images/10-2.webp" width="32%"> <img src="images/10-3.webp" width="32%">

```text
风格:暗色极光上的磨砂玻璃与液态透镜。
画面:#060316底+暗角;#923EDA/#4558F4/#74D8FC柔光斑缓流;2-3张圆角玻璃卡错层,亮描边、柔投影、高光扫过。
字体:细无衬线,白/半透明两级,标题宽字距。
动效:30fps顺滑;镜头慢推+3D倾斜视差;卡片错峰0.5s入场;文字逐行0.4s由糊变清;透镜游走放大1.3倍带色散;收尾卡片虚焦,光环0.6s扩散后静持。
实现:WebGL噪声渐变+折射着色器;backdrop-filter。
不要:白底扁平;实心卡;硬切。
内容:{在这里写你的内容}
```

<details><summary>English prompt</summary>

```text
Style: frosted-glass cards floating over a dark aurora; a liquid lens refracts content.
Visuals: #060316 base + vignette; soft drifting blobs of #923EDA/#4558F4/#74D8FC; 2-3 large-radius translucent glass cards layered in depth, bright rim, soft shadow, diagonal specular sweep.
Type: light sans, white + translucent tier; closing title ultra-light, wide tracking.
Motion: smooth full 30fps; slow push-in with 3D tilt parallax; cards stagger in 0.5s apart; text lines resolve blur-to-sharp, 0.4s each; lens glides, magnifying 1.3x with chromatic fringing; outro: cards defocus, lens lands on title, halo expands 0.6s, then 1s hold.
Build: WebGL noise gradient + refraction shader; backdrop-filter blur; perspective.
Avoid: flat white; opaque cards; hard cuts; neon outlines.
Content: {your content here}
```

</details>

## 11 · 几何构成包豪斯 <sub>Geometric Bauhaus Construction</sub>

> 三原色几何块踩着节拍在网格上搭建

<img src="images/11-1.webp" width="32%"> <img src="images/11-2.webp" width="32%"> <img src="images/11-3.webp" width="32%">

```text
风格:包豪斯几何构成,按网格逐拍搭成海报
画面:米纸#F7F1E3淡网格;红#DC2F35黄#F6C60C蓝#2552A3黑#111111平涂;只用圆/扇形/方/三角/粗条,吸附120px模块
字体:粗黑几何无衬线大写,可竖排;注释小字宽距
动效:120BPM,15帧一拍,每拍一个动作;缓入缓出,落定无回弹,带运动模糊;新形先现对位十字再展开;可整组绕支点转动重排;转场=逐格翻转散开再拼新构图
实现:帧号÷15查拍号状态表;坐标取模块整数倍
不要:渐变阴影圆角;多处同动;离网格
内容:{在这里写你的内容}
```

<details><summary>English prompt</summary>

```text
Style: Bauhaus geometric construction; a poster assembled on a grid, one beat at a time
Visual: cream paper #F7F1E3 with faint grid; flat red #DC2F35, yellow #F6C60C, blue #2552A3, black #111111; only circles, quarter-circles, squares, triangles, thick bars, snapped to a 120px module
Type: heavy geometric sans caps, may run vertical; small wide-tracked captions
Motion: 120 BPM, 15 frames per beat, one action per beat; ease-in-out, settle with no bounce, motion blur on moves; a registration crosshair appears first, then the shape unfolds from it; whole cluster may rotate about a pivot to re-compose; transition = cells flip and scatter, then reassemble into a new layout
Build: beat = floor(frame/15) indexes a state table; coordinates are integer multiples of the module
Avoid: gradients, shadows, rounded corners; several things moving at once; off-grid placement
Content: {your content here}
```

</details>

## 12 · 复古Synthwave <sub>Retro Synthwave VHS</sub>

> 霓虹网格落日,录像带回放

<img src="images/12-1.webp" width="32%"> <img src="images/12-2.webp" width="32%"> <img src="images/12-3.webp" width="32%">

```text
风格:80年代Synthwave+VHS回放
画面:夜空#190A21;洋红网格#FF3CC8一点透视;条纹落日#FFE27A→#EC5655;青线框山#82EAFF;对称,强bloom
字体:粗宽铬字(蓝金镜面+星芒扫光);副行霓虹草书
动效:30fps连续;网格匀速滚向镜头;开场4:3噪点画框撑满;标题巨大推入7帧落定+闪白1帧;霓虹字闪2-3下点亮;每2-3s撕裂2帧;结尾CRT关机→光点
实现:Three.js网格+着色器落日;Bloom+扫描线+色差+噪点;角落VHS时间码
不要:无辉光;网格静止;噪点糊主体
内容:{在这里写你的内容}
```

<details><summary>English prompt</summary>

```text
Style: 80s synthwave via VHS playback
Look: night #190A21; magenta grid #FF3CC8, one-point perspective; striped sun #FFE27A→#EC5655; cyan wireframe hills #82EAFF; symmetric, strong bloom
Type: wide heavy chrome letters (blue-gold mirror + star-glint sweep); secondary line in neon script
Motion: smooth 30fps; grid scrolls toward camera at constant speed; open on noisy 4:3 frame expanding to full; headline flies in huge, settles in 7 frames + 1-frame white flash; neon text flickers 2-3x to power on; 2-frame horizontal tear every 2-3s; end with CRT power-off to line → dot
Build: Three.js grid + shader sun; bloom + scanlines + chromatic aberration + noise; corner VHS timecode
Avoid: no glow; static grid; noise smearing the subject
Content: {your content here}
```

</details>

## 13 · 像素风 <sub>16-bit Pixel Art</sub>

> 低分辨率逐点画,CRT 里的日夜换色

<img src="images/13-1.webp" width="32%"> <img src="images/13-2.webp" width="32%"> <img src="images/13-3.webp" width="32%">

```text
风格:16位游戏机像素画,套CRT外壳。
画面:320×180逐点画放大4倍;≤32色,渐变用Bayer抖动;多层视差;#1F1A30 #3D438B #BF2964 #F5C542 #339245。
字体:点阵字;标题黄橙渐变+深红厚投影;正文入框逐字打。
动效:只走整数像素;色表每2秒整套硬切;CRT开机进、关机出;推镜1×→2×硬切;高潮闪白1帧接抖动放射光;标题4帧砸落。
实现:Canvas低分辨率绘制,关平滑放大;LUT换色;扫描线+桶形畸变+暗角。
不要:亚像素移动、抗锯齿、淡入淡出、矢量字。
内容:{在这里写你的内容}
```

<details><summary>English prompt</summary>

```text
Style: 16-bit console pixel art, framed inside a CRT.
Visuals: paint at 320×180, 4× nearest-neighbor upscale; ≤32 colors per screen, gradients only as Bayer dither bands; multi-layer parallax; #1F1A30 #3D438B #BF2964 #F5C542 #339245.
Type: bitmap font; titles chunky, yellow→orange gradient + thick dark-red shadow; body text in a double-bordered box, typed per character.
Motion: integer-pixel moves only, far layer 1px per 4 frames; hard whole-palette swap every ~2s (day→night); CRT power-on in, power-off out; push-in as hard 1×→2× cut; climax = 1 white frame, then dithered radial light burst; titles slam down in 4 frames.
Build: Canvas low-res render + imageSmoothingEnabled=false; LUT palette swaps; scanlines + barrel distortion + vignette.
Avoid: sub-pixel smooth motion, anti-aliasing, opacity fades, vector fonts.
Content: {your content here}
```

</details>

## 14 · 液态流动 <sub>Liquid Motion</sub>

> 果冻般可捏的液体,粘连拉丝融合弹跳

<img src="images/14-1.webp" width="32%"> <img src="images/14-2.webp" width="32%"> <img src="images/14-3.webp" width="32%">

```text
风格:SDF 融球液态,一切都是可捏的高光果冻
画面:李子紫底#3F1142压暗角;液体橙#E8582E→洋红#E0146E→紫#9B1FD6;半透明+强高光+菲涅尔边光;镜面地面倒影
字体:粗衬线小写,同材质果冻字挂液滴
动效:流畅30fps;拉丝断颈坠落,落地冠状飞溅;相邻形状平滑融合、交界混色;弹簧过冲约15%、0.5s收住,静止仍微颤;转场=液浪擦屏约4帧,或聚团爆开+冲击环
实现:WebGL raymarch SDF+smin,算高光/折射/倒影
不要:扁平填色;硬边不相融;线性匀速;冷色
内容:{在这里写你的内容}
```

<details><summary>English prompt</summary>

```text
Style: SDF metaball liquid; everything is glossy, squeezable jelly
Look: plum bg #3F1142 with dark vignette; liquids orange #E8582E → magenta #E0146E → violet #9B1FD6; translucent, hard specular, fresnel rim; mirror floor reflections, centered
Type: bold lowercase serif in the same jelly material, drips on the baseline
Motion: smooth 30fps; stretch, pinch-off and fall, crown splash on landing; neighbours smooth-merge with blended seams; spring ~15% overshoot settling in 0.5s, idle wobble; transitions = liquid surge wipe (~4 frames) or fuse into one blob, burst + shockwave ring
Build: WebGL raymarched SDF + smin, normals for specular/refraction/floor reflection
Avoid: flat fills; hard shapes that never merge; linear motion; cold palette
Content: {your content here}
```

</details>

## 15 · 综艺花字 <sub>Variety Show Captions</sub>

> 多层描边弹跳花字,按情绪放大笑点

<img src="images/15-1.webp" width="32%"> <img src="images/15-2.webp" width="32%"> <img src="images/15-3.webp" width="32%">

```text
风格:综艺花字,9:16;实拍垫底,每段情绪换一套花字。
画面:#FFE14A #EC2580 #3ED3EE,#1C1D5D 描边;爆炸星、放射底、斜纹底,抠像加白贴纸边。
字体:超粗圆体;渐变字面+白描边+彩色外描边+硬投影。
动效:30fps;逐字弹出过冲 1.2→1,隔 2 帧;表情贴错落弹入;横幅斜甩带拖影;重拍 1 帧白闪;印章 1.6 倍砸落;彩条斜扫 6 帧转场。
实现:DOM+SVG,多重描边,spring 缩放旋转,conic-gradient 放射底。
不要:单层描边;线性匀速;全片一套字效;字挡主体。
内容:{在这里写你的内容}
```

<details><summary>English prompt</summary>

```text
Style: variety-show captions, 9:16; full-bleed live footage underneath, a different caption kit per emotional beat.
Look: #FFE14A #EC2580 #3ED3EE, #1C1D5D outlines; starbursts, rotating sunburst bg, diagonal-stripe bg, cutout subject with white sticker border.
Type: extra-bold rounded; gradient fill + white stroke + colored outer stroke + hard drop shadow.
Motion: 30fps; per-character pop-in overshoot 1.2→1, 2-frame stagger; emoji stickers pop in staggered; banners swing in tilted with motion smear; 1-frame white flash on hits; stamps slam from 1.6×; 6-frame diagonal color-band wipe transitions.
Build: DOM+SVG, stacked strokes, spring-driven scale/rotate, conic-gradient sunburst.
Avoid: single-layer stroke; linear easing; one caption kit for the whole piece; text covering the subject.
Content: {your content here}
```

</details>

## 版权说明
截图版权归原视频作者,仅作风格研究引用;提示词为观察后重新撰写。
