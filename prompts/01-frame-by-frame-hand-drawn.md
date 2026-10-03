# 01 · 逐帧手绘 / Frame-by-Frame Hand-Drawn

> 一拍二线条沸腾,纸上的手温

## 中文提示词

风格:逐帧手绘,线条沸腾。
画面:纸纹米底#EEE1BE;红#D33631黄#F2C429平涂,墨黑#1D1512粗描边;主体后柔光晕#ECDA98;排线阴影。
字体:如需文字:圆胖手写粗体逐笔写出。
动效:默认on 2s,快动作on 1s,定格on 3s;每张新图线抖±2px;挤压拉伸、残影、速度线;高潮插1-2帧满屏星爆冲击;景别硬切不推拉。
实现:Canvas笔刷;以floor(frame/step)为种子抖路径与线宽,位置按step取整。
不要:丝滑缓动;矢量死线;渐变;定格内乱抖。
内容:{在这里写你的内容}

## English Prompt

Style: frame-by-frame hand-drawn cartoon, boiling lines.
Look: grainy cream paper #EEE1BE; flat red #D33631 and yellow #F2C429 fills, thick ink #1D1512 outlines, soft glow #ECDA98 behind the subject; hatched shadows.
Type: if text is needed: chunky rounded hand-lettering written on stroke by stroke.
Motion: on 2s by default, fast actions on 1s, holds on 3s; each new drawing jitters lines ±2px; squash & stretch, smears, speed lines; climax gets 1-2 full-screen starburst impact frames; hard cuts between shot sizes, no zooms.
Build: Canvas brush; floor(frame/step) seeds path and stroke-width jitter; positions quantized to the step.
Avoid: silky easing; dead vector lines; gradients; jitter within one held drawing.
Content: {your content here}
