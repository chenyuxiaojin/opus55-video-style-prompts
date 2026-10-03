# 04 · 线条动画 / Single-Line Art

> 一根金线不离纸,留白即画面

## 中文提示词

风格:一根金线一笔画到底,大留白
画面:底 #151E2D→#070E16 暗角;线 #C9B27E 2px;笔尖 #FFF8E8 光点;末个闭合形填金 #E4D3A0
字体:如需文字:宽字距细衬线,定版后淡入
动效:30fps 连续;笔尖匀速,拐角停 5 帧;镜头跟笔;新线亮白 1s 退成金;闭合时3帧由外向内填满+光环外扩;再 0.8s 拉远定版
实现:SVG单path+stroke-dashoffset;getPointAtLength 定光点与相机
不要:多条线;断笔;提前填色;快切
内容:{在这里写你的内容}

## English Prompt

Style: one gold line drawn without lifting, lots of negative space
Look: radial bg #151E2D→#070E16 vignette; line #C9B27E 2–3px round caps; white-hot tip #FFF8E8; only the final closed shape fills gold #E4D3A0
Type: if text is needed: after lockup, wide-tracked thin serif caps centered below, blur-fade in
Motion: smooth 30fps; tip near-constant speed, holds 4–6 frames at corners; camera pans with tip; fresh line glows white, fades to gold over 1s; on closure, 3-frame outside-in fill + expanding glow ring; then 0.8s ease-in-out pull-back to lockup
Build: single SVG path + stroke-dashoffset; getPointAtLength drives tip glow and camera
Avoid: multiple lines; breaks or jumps; early fills; hard cuts or shake
Content: {your content here}
