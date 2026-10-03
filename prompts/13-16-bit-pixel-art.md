# 13 · 像素风 / 16-bit Pixel Art

> 低分辨率逐点画,CRT 里的日夜换色

<img src="../images/13-1.webp" width="32%"> <img src="../images/13-2.webp" width="32%"> <img src="../images/13-3.webp" width="32%">

## 中文提示词

风格:16位游戏机像素画,套CRT外壳。
画面:320×180逐点画放大4倍;≤32色,渐变用Bayer抖动;多层视差;#1F1A30 #3D438B #BF2964 #F5C542 #339245。
字体:点阵字;标题黄橙渐变+深红厚投影;正文入框逐字打。
动效:只走整数像素;色表每2秒整套硬切;CRT开机进、关机出;推镜1×→2×硬切;高潮闪白1帧接抖动放射光;标题4帧砸落。
实现:Canvas低分辨率绘制,关平滑放大;LUT换色;扫描线+桶形畸变+暗角。
不要:亚像素移动、抗锯齿、淡入淡出、矢量字。
内容:{在这里写你的内容}

## English Prompt

Style: 16-bit console pixel art, framed inside a CRT.
Visuals: paint at 320×180, 4× nearest-neighbor upscale; ≤32 colors per screen, gradients only as Bayer dither bands; multi-layer parallax; #1F1A30 #3D438B #BF2964 #F5C542 #339245.
Type: bitmap font; titles chunky, yellow→orange gradient + thick dark-red shadow; body text in a double-bordered box, typed per character.
Motion: integer-pixel moves only, far layer 1px per 4 frames; hard whole-palette swap every ~2s (day→night); CRT power-on in, power-off out; push-in as hard 1×→2× cut; climax = 1 white frame, then dithered radial light burst; titles slam down in 4 frames.
Build: Canvas low-res render + imageSmoothingEnabled=false; LUT palette swaps; scanlines + barrel distortion + vignette.
Avoid: sub-pixel smooth motion, anti-aliasing, opacity fades, vector fonts.
Content: {your content here}
