# 02 · 等轴2.5D / Isometric 2.5D

> 桌面微缩模型,一格一格自己长出来

<img src="../images/02-1.webp" width="32%"> <img src="../images/02-2.webp" width="32%"> <img src="../images/02-3.webp" width="32%">

## 中文提示词

风格:等轴2.5D桌面微缩模型,逐格自己长出来
画面:正交等轴无透视;万物落在方格地块+厚底座;先素白#EDE8F5配深靛#1B1650,高潮从中心一波上色#A4EDC4/#9F86DF/#62EFF1;圆角块、软阴影
字体:粗圆3D挤出字平贴地面;等宽小字注释;白底数据卡+引线
动效:30fps连续带运动模糊,相机慢漂。地块由中心逐环错峰飞入(2s);物件逐格拔高,先线框后实体,轻过冲(3s);光环脉冲0.5s内上色;末尾拉远,字母逐个弹落
实现:Three.js正交相机+InstancedMesh
不要:透视、写实材质、满屏霓虹、同时出现
内容:{在这里写你的内容}

## English Prompt

Style: isometric 2.5D tabletop miniature that builds itself tile by tile
Look: orthographic iso, no perspective; everything sits on a tile grid over a thick base slab; start white clay #EDE8F5 with deep indigo #1B1650, then a color wave spreads from center at the climax (mint #A4EDC4 / violet #9F86DF / cyan glow #62EFF1); rounded blocks, soft shadows
Type: chunky rounded 3D-extruded letters lying flat on the ground; small monospace notes; white data cards with leader lines
Motion: continuous 30fps with motion blur, slow camera drift. Tiles fly in ring by ring from center (2s); objects rise per cell, wireframe first then solid, slight overshoot (3s); a ring pulse recolors all within 0.5s; finally pull back, letters drop in one by one with a bounce
Build: Three.js orthographic camera + InstancedMesh
Avoid: perspective, realistic materials, neon everywhere, everything at once
Content: {your content here}
