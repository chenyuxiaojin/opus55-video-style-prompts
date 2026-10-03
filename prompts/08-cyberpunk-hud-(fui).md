# 08 · 赛博朋克HUD / Cyberpunk HUD (FUI)

> 暗底青光细线界面,高潮一瞬转琥珀

## 中文提示词

风格:科幻FUI发光细线仪表盘。
画面:#03080A底,#2EE6E6主线,#0F4F55暗线,#EAFBFF数字,高潮转#FF9A1F。主体套分段刻度环+准星,两侧数据栏+角括号,蜂窝底纹+辉光。
字体:等宽全大写,小标签配大数字。
动效:30fps连续。CRT开机进、压线成点出(各0.3s);弧段描边,逐行打字;数字乱跳后落定。转折2帧切片+RGB分离;高潮白闪1帧→3帧转琥珀→推镜后硬切回。
实现:Three.js线框+Bloom;SVG描边;种子随机乱码。
不要:无辉光;多色;实心块;圆体字。
内容:{在这里写你的内容}

## English Prompt

Style: sci-fi film FUI — glowing hairline instrument panels on near-black.
Visual: bg #03080A, lines #2EE6E6, dim #0F4F55, big numerals #EAFBFF, climax shifts to #FF9A1F. Subject wrapped in segmented tick rings + crosshair; side data columns, corner brackets, faint hex grid, bloom.
Type: monospace, uppercase, wide tracking; tiny labels vs big numerals.
Motion: smooth 30fps. CRT power-on in, power-off squeeze-to-dot out (0.3s each); arcs draw on, lines type with cursor; numbers scramble then settle and tick. Beat change: 2-frame slice offset + RGB split. Climax: 1-frame white flash → shockwave → amber in 3 frames → push-in, hard snap back.
Build: Three.js wireframe + bloom pass; SVG stroke draw; seeded-random glyph scramble.
Avoid: no glow; many hues; big solid fills; rounded fonts.
Content: {your content here}
