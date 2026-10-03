# 05 · 3D 渲染·软糯物理 / 3D Render — Soft Physics

> 糖果色充气字砸进胶囊地毯，软糯又有分量

## 中文提示词

# 风格：3D 渲染·软糯物理
做一条约 10 秒 16:9 的三维渲染动画，主题 {主题}。气质：糖果色、软糯、有分量，像广告级物理模拟 CG。

## 视觉
- 场景：数千颗竖立双色胶囊排成网格，铺到地平线，低机位看像一排排珠子；胶囊上半奶油米 #F6E3D6、下半薰衣草紫 #A98BEB。
- 主体：{标题文字} 做成充气软糖感的圆胖 3D 字，全圆角，玫红 #E0306C，清漆高光+微次表面，暗部 #A8144A。
- 重物：镜面铬球 {核心物件}，反射粉紫环境，软硬对比。
- 光：大面积柔光、软短阴影、缝隙 AO；远景粉紫雾 #E6C2DC，天空无细节渐变。
- 镜头：贴地微距、浅景深、轻 bloom 与暗角。

## 字体与构图
主字用胖圆小写无衬线，占画宽 50–60%、略高于中线，重物停在字尾当句号。收尾副标：全大写宽字距（约 0.3em）细体英文 + 短细线 + 一行中文小字，深灰紫 #3A2E3E，垫淡白柔光，居下 1/4。先微距局部，结尾正面居中对称定版。

## 动效
1. 0–2s：首个元素从画外落下，下落纵向拉伸+运动模糊，触地挤压下陷，胶囊被压开，一圈粉色 #F7A6C4 涟漪向外扩散；镜头后拉抬升。
2. 2–5s：其余元素依次落下，间隔渐短（约 1s→0.5s），每次弹簧回弹带轻微过冲和新涟漪；镜头缓慢环绕。
3. 6.5–8.5s：重物加速坠下砸在字尾，周围胶囊炸起翻滚、落回翻成紫色面，紫色由落点扩散到全场；重物几乎不弹。
4. 8.5–10s：正面定版，副标 0.6s 淡入微上浮，静止留白。
物理驱动（重力、阻尼弹簧、碰撞让位），不用线性；30fps 连续，不做一拍二。

## 实现提示
Three.js `InstancedMesh(CapsuleGeometry)` 逐实例写下沉/旋转/颜色，涟漪 = 随时间外扩的环形衰减；翻色 = 预计算抛物线+绕水平轴转 180°；字用大 bevel 的 TextGeometry + `MeshPhysicalMaterial`(clearcoat)；铬球 metalness 1、roughness≈0 + 环境贴图；后期 DOF + Bloom + SSAO。物理按帧号解析或预烘焙（Remotion 用 @remotion/three），或 Blender+Python 建模 Cycles 渲染。

## 不要
扁平图形、描边卡通、硬阴影、纯黑底、霓虹色；字不能像硬塑料壳；不加 UI 框和图标。

## English Prompt

# Style: 3D Render — Soft Physics
Make a ~10s 16:9 3D-rendered animation about {topic}. Mood: candy-colored, squishy, weighty — ad-grade physics-sim CG.

## Visual
- Set: thousands of upright two-tone capsules in a grid stretching to the horizon; from a low camera they read as rows of beads. Capsule halves: cream #F6E3D6 / lavender #A98BEB.
- Hero: {title_text} as chubby inflated gummy 3D letters, fully rounded, hot pink #E0306C, clearcoat highlights + slight subsurface, shadows #A8144A.
- Heavy object: a mirror-chrome sphere as {core_object}, reflecting the pink-lilac world — soft vs. hard.
- Light: large soft lighting, short soft shadows, AO in the gaps; pink-lilac haze #E6C2DC at the horizon, featureless gradient sky.
- Camera: ground-hugging macro, shallow DOF, light bloom and vignette.

## Type & composition
Hero word in rounded chubby lowercase sans, 50–60% of frame width, slightly above center; the heavy object rests at the end like a period. End caption: ALL-CAPS light sans with ~0.3em tracking + short hairline + one small secondary-language line, dark plum-gray #3A2E3E over a faint white glow band, lower quarter. Open on a macro detail, end on a frontal centered symmetrical lock-up.

## Motion
1. 0–2s: first element drops in from off-frame, stretched with motion blur, squashes and sinks on impact, pushing capsules aside; a pink #F7A6C4 ripple radiates outward; camera pulls back and rises.
2. 2–5s: remaining elements drop with shrinking gaps (~1s→0.5s), each with spring rebound (slight overshoot) and a new ripple; slow camera orbit.
3. 6.5–8.5s: heavy object accelerates down and slams at the word's end; nearby capsules blast up, tumble and land flipped lavender-up; lavender spreads from impact across the field; the heavy object barely bounces.
4. 8.5–10s: frontal lock-up, caption fades in over 0.6s with slight rise, hold.
Physics-driven (gravity, damped springs, collision displacement), never linear; continuous 30fps, not on twos.

## Implementation
Three.js `InstancedMesh(CapsuleGeometry)` with per-instance sink/rotation/color; ripple = ring falloff expanding over time; recolor = precomputed ballistic arc + 180° flip about a horizontal axis; letters via TextGeometry with big bevel + `MeshPhysicalMaterial` (clearcoat); chrome metalness 1, roughness≈0 + env map; post DOF + Bloom + SSAO. Drive physics from frame number analytically or pre-baked (Remotion: @remotion/three), or model in Blender+Python and render in Cycles.

## Don't
Flat graphics, outlined cartoon, hard shadows, pure black backgrounds, neon colors; letters must not feel like rigid plastic; no UI frames or icons.
