# 02 · 等轴 2.5D 微缩沙盘 / Isometric 2.5D Diorama

> 正交俯视的桌面微缩沙盘,一格格长出、先白后彩

## 中文提示词

# 风格:等轴 2.5D 桌面微缩模型(Isometric Diorama)

把 {主题} 做成一块摆在桌上的等轴微缩沙盘,约 10 秒,一格一格"长"出来。

## 视觉语言
- 机位:Three.js 正交相机(OrthographicCamera),经典等轴角(绕 Y 轴 45°、俯角约 35.26°),全程不换角度、没有透视;只做平移和缩放。
- 地基:N×N 方块瓦片(建议 12×12),每块是小圆角倒角的方砖,缝隙 2-3px 深色;沙盘下有 2-3 层淡紫厚底座(蛋糕分层)和柔和接触阴影,像浮在桌面上。
- 材质:哑光黏土感(MeshStandardMaterial,roughness≈0.8),柔光 + 环境光遮蔽,影子软而偏紫。
- 配色分两幕:前半段"白模"——全场几乎只有淡紫白 #ECE8F4,只留 {核心物件} 用深靛 #221C66 当唯一重色,点缀少量薄荷绿 #7ED9A0、钴蓝 #4A5BD0;后半段"上色"——马卡龙色铺满:薄荷绿地块、珊瑚 #E98A6E、奶黄 #F2D98A、天蓝 #8FBDF0、道路紫 #6B5BC8,背景从灰白 #E4E2EE 变成上浅下深的紫色渐变(#D9C8F0→#9F84E2)。
- 能量色:青色 #5CE6E0 只用于发光——开场的蓝图网格线、{核心物件} 上的光环、瓦片缝里流动的光线。

## 字体排印
- 标题 {标题文字}:超粗、偏宽的几何无衬线,做成深靛色立体挤出字,平躺在等轴地面上,沿等轴斜线排列。
- 辅助行:中文副标题 + 全大写等宽英文,字距拉开,用"·"分隔,前面一个青色状态点。
- 数据卡:白色卡片放在 3D 空间里(跟随等轴面倾斜),左边一条彩色竖条,中文标签 + 等宽英文小标,超粗大号数字 + 小单位,旁边一组迷你柱状图;用细引线 + 圆点锚定到场景里的物件上。

## 动效与节奏(10 秒五幕)
1. 0-0.5s 青色蓝图网格淡入,中心 2×2 深色"种子"方块翻滚落下。
2. 0.5-2s 瓦片按"一圈一圈从中心向外"的顺序从高处砸下,带竖向运动模糊,落地轻微回弹(推测 easeOutBack);相机同时从特写拉远到整块沙盘。
3. 2-5.5s 白模阶段:{次要物件} 逐个弹出(scale 0→1),高楼分段伸缩式长高,先立脚手架再长实体;相机缓慢平移跟拍,节奏卡拍(推测按固定 BPM 量化)。
4. 5.5-8s 高潮:{核心物件} 冒出光环脉冲和向上光柱 → 一圈颜色波从中心向外扩散,把白模一格格染成彩色,背景同步变饱和紫;随后 2-3 张数据卡依次弹出,数字滚动递增。
5. 8-10s 数据卡收走,相机拉远,沙盘移到右侧;标题字母一个个从空中落到地面(先见影子后见字),最后画出下划线、打出副标题。

## 招牌手法 / 实现提示
- 落砖波:每块瓦片延迟 = 到中心的切比雪夫距离 × 40-60ms,y 从 +8 落到 0。
- 运动模糊:Remotion 的 <Trails>/多次采样,或在 Three.js 里对位移画半透明残影。
- 上色波:着色器里按 distance(uv, center) < progress 混合白模色与目标色,波前加一圈青色描边。
- 数字滚动:interpolate 帧数 → toFixed。

## 该做 / 不该做
- 该做:一切对齐网格;重色只给一个主角;先白后彩讲"从草图到活过来"。
- 不该做:透视相机、写实贴图、硬阴影;青色只用于发光;字不要贴在屏幕平面上,要"躺"在等轴世界里。

## English Prompt

# Style: Isometric 2.5D Desktop Diorama

Make a ~10s animation about {topic}: {topic} is shown as a tiny isometric model sitting on a desk, growing tile by tile.

## Visual language
- Camera: Three.js OrthographicCamera at the classic isometric angle (45° yaw, ~35.26° pitch). Never change the angle, no perspective; only pan and zoom.
- Base: an N×N grid of tiles (suggest 12×12), each a small rounded-bevel block with dark 2-3px seams. Under the board, 2-3 layered lavender slabs (like a layer cake) and a soft contact shadow so it floats above the floor.
- Material: matte clay/plastic (MeshStandardMaterial, roughness ~0.8), soft light + ambient occlusion, short soft violet-tinted shadows, no hard specular.
- Two-act palette. Act 1 "white clay": almost everything lavender-white #ECE8F4; only {core object} gets deep indigo #221C66 as the single heavy color; tiny accents of mint #7ED9A0 and cobalt #4A5BD0. Act 2 "colored": macaron colors everywhere - mint ground, coral #E98A6E, butter #F2D98A, sky blue #8FBDF0, road violet #6B5BC8; background shifts from pale grey-lavender #E4E2EE to a vertical violet gradient (#D9C8F0 → #9F84E2).
- Energy color: cyan #5CE6E0, used only for light - the intro blueprint grid, rings around {core object}, light flowing along tile seams.

## Typography
- Title {title text}: ultra-bold, wide geometric sans, extruded in deep indigo, lying flat on the isometric ground and running along an iso axis.
- Support line: a Chinese/primary-language subtitle + uppercase monospaced English with wide tracking, "·" separators, a cyan status dot in front.
- Data cards: white cards placed in 3D (tilted with the iso plane), a colored vertical stripe on the left, a label + small mono caption, a huge ultra-bold number + small unit, a mini bar chart; tied to objects in the scene with a thin leader line and dot anchor.

## Motion & rhythm (10s, five beats)
1. 0-0.5s cyan blueprint grid fades in; a dark 2×2 "seed" of tiles tumbles down at the center.
2. 0.5-2s tiles slam down ring by ring from the center outward, with vertical motion blur and a slight landing bounce (guess: easeOutBack); the camera pulls back from a close-up to the whole board.
3. 2-5.5s white-clay stage: small houses, trees, {secondary objects} pop in (scale 0→1); towers grow telescopically floor by floor, scaffolding first, then solids; slow camera pan; timing locked to a beat (guess: quantized to a fixed BPM).
4. 5.5-8s climax: {core object} emits ring pulses and an upward light beam → a color wave spreads from the center, dyeing the white model tile by tile, background saturates to violet; then 2-3 data cards pop in one after another with counting-up numbers.
5. 8-10s cards leave, camera pulls back, the diorama slides right; title letters drop one by one from the air onto the ground (shadow first, then letter), then an underline draws and the subtitle types on.

## Signature techniques / implementation hints
- Drop wave: per-tile delay = Chebyshev distance to center × 40-60ms, y from +8 to 0.
- Motion blur: Remotion <Trails>/multi-sample, or semi-transparent afterimages of displacement in Three.js.
- Color wave: in a shader, mix clay color and target color where distance(uv, center) < progress, with a cyan rim on the wavefront.
- Counting numbers: interpolate frame → toFixed.

## Do / Don't
- Do: snap everything to the grid; give the heavy color to one hero only; tell a "sketch → comes alive" story via white-then-color.
- Don't: perspective camera, realistic textures, hard shadows, random neon; never use cyan for anything except light; don't stand text upright on the screen plane - lay it in the isometric world.
