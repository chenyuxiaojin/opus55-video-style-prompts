# 11 · 几何构成包豪斯 / Geometric Bauhaus Construction

> 三原色几何块踩着节拍在网格上搭建

## 中文提示词

风格:包豪斯几何构成,按网格逐拍搭成海报
画面:米纸#F7F1E3淡网格;红#DC2F35黄#F6C60C蓝#2552A3黑#111111平涂;只用圆/扇形/方/三角/粗条,吸附120px模块
字体:粗黑几何无衬线大写,可竖排;注释小字宽距
动效:120BPM,15帧一拍,每拍一个动作;缓入缓出,落定无回弹,带运动模糊;新形先现对位十字再展开;可整组绕支点转动重排;转场=逐格翻转散开再拼新构图
实现:帧号÷15查拍号状态表;坐标取模块整数倍
不要:渐变阴影圆角;多处同动;离网格
内容:{在这里写你的内容}

## English Prompt

Style: Bauhaus geometric construction; a poster assembled on a grid, one beat at a time
Visual: cream paper #F7F1E3 with faint grid; flat red #DC2F35, yellow #F6C60C, blue #2552A3, black #111111; only circles, quarter-circles, squares, triangles, thick bars, snapped to a 120px module
Type: heavy geometric sans caps, may run vertical; small wide-tracked captions
Motion: 120 BPM, 15 frames per beat, one action per beat; ease-in-out, settle with no bounce, motion blur on moves; a registration crosshair appears first, then the shape unfolds from it; whole cluster may rotate about a pivot to re-compose; transition = cells flip and scatter, then reassemble into a new layout
Build: beat = floor(frame/15) indexes a state table; coordinates are integer multiples of the module
Avoid: gradients, shadows, rounded corners; several things moving at once; off-grid placement
Content: {your content here}
