# 14 · 液态流动 / Liquid Motion

> 糖果色果冻液滴在暗紫镜面上坠落、融合、成字

## 中文提示词

做一条约 10 秒的「液态流动」风格动画,主题 {主题},结尾落版 {标题文字} + {副标语}。

**视觉语言**
- 暗紫摄影棚:背景 #4A0E50 中心微亮、四角压暗到 #2A0730;下方近黑镜面地板 #12031A,液体都有随距离变虚的倒影。
- 主角是半透明高饱和果冻液体,四色:橘红 #F0603A、珊瑚 #E8455A、玫红 #E0186E、电光紫 #9B2FE0。要「饱满得像能捏起来」:菲涅尔亮边、一条窗形白色硬高光、内部柔和透光;异色融合后内部有色块漩涡。
- 液滴折射身后物体,透过它看到的 {核心物件} 被放大且倒置。
- 低机位贴地、浅景深,前景水珠虚焦,快速运动带运动模糊。

**字体排印**
- {标题文字} 用粗壮小写复古衬线体,每个字母鼓成果冻立体字,四色逐字分配,字内有小气泡,底边挂液珠。
- 副标语在右下:白色宋体中文 + 一行全大写宽字距小号无衬线英文。

**构图**
主体居中或沿地平线横排,地平线在下 1/3;落版标题约占半屏宽,留大片暗紫负空间。

**动效语言**(一镜到底,不硬切)
1. 液滴拉丝垂挂,颈部断开,加速下坠。
2. 落地压扁,溅起皇冠水花;其他颜色接连落下。
3. 液饼靠近,先拉细颈粘连再融合,内部颜色搅拌。
4. 融合体弹起成球、弹簧晃动;镜头穿过液面进入粉色液体内部(光束 + 漂浮颗粒),再用柔软液态擦除回到暗紫棚。
5. 四色液珠排一排抖动,粘成胶囊后炸开成 {标题文字},背后升起桃色溅冠和粉色径向冲击环。
6. 字持续微晃,一滴从字底拉丝滴落,地面起同心涟漪,副标语淡入,静帧约 2 秒。
- 每个动作 0.75–1.5 秒;落定用欠阻尼弹簧(轻过冲 2–3 次),坠落用 ease-in;顺滑 60fps,不要一拍二。

**实现提示**
- WebGL 片元着色器光线步进:球/胶囊 SDF 用 smin 融合,菲涅尔 + Blinn 高光,地面做反射 + 距离模糊;标题用 SDF 文字挤出并圆角膨胀。
- 参数全部由帧号驱动(Remotion 用 useCurrentFrame 传 uniform)。
- 低成本替代:SVG goo 滤镜(feGaussianBlur + feColorMatrix 阈值)+ 径向渐变高光。

**该做 / 不该做**
- 该做:每次接触都有挤压拉伸、拉丝和倒影;颜色只在四种液体色里轮换。
- 不该做:扁平矢量水滴、硬描边、冷色蓝绿水、线性运动、硬切。

## English Prompt

Create a ~10-second, 1920×1080 animation in a "Liquid Motion" style. Topic: {topic}. End on a logo lockup of {title_text} plus a one-line {tagline}.

**Visual language**
- The set feels like a dark purple photo studio: deep grape-purple background #4A0E50, slightly brighter in the center, vignetted to #2A0730 at the corners; below it a near-black glossy mirror floor #12031A. Every liquid shape casts a clear reflection that softens with distance.
- All subjects are translucent, highly saturated jelly liquid in four colors: orange-red #F0603A, coral #E8455A, hot magenta #E0186E, electric violet #9B2FE0. The material must look "so plump you could pinch it": fresnel-brightened rims, one hard white window-shaped specular streak, soft subsurface glow inside, a thin light inner rim. When colors merge, swirling color patches flow inside the blob.
- Drops refract what is behind them: {core_object} or text seen through a drop appears magnified and flipped upside down.
- Low camera skimming the floor, shallow depth of field, out-of-focus droplets in the foreground; motion blur on fast moves.

**Typography**
- The final {title_text} is a chunky lowercase serif (soft, bracketed, retro serif), each letter an inflated 3D jelly glyph, the four liquid colors assigned letter by letter, tiny bubbles inside, liquid beads hanging from the bottom edges about to drip.
- The tagline sits lower right: white CJK/Song-style serif at medium weight, plus one line of small all-caps sans with wide tracking.

**Composition**
- Subjects stay centered or lined up horizontally along the horizon; horizon in the lower third. At the lockup the title spans about half the frame width with plenty of dark purple negative space.

**Motion language** (one continuous camera story, no hard cuts)
1. A drop hangs from the top on a stretched string, the neck thins and snaps, it falls with gravity (ease-in).
2. It squashes into a puddle on impact, throwing a crown splash and tiny beads; drops of other colors fall one after another.
3. Puddles slide toward each other, first linking with a thin neck, then fusing (smooth-min metaballs) while colors stir inside.
4. The fused blob bounces up into a sphere, wobbles on an underdamped spring and lands; the camera pushes through its surface into a pink inside-the-liquid world (god rays, floating particles), then a soft liquid wipe returns to the dark purple studio.
5. Four colored beads in a row jiggle, link into one capsule, then burst into {title_text}: a peach splash crown rises behind it with a pink radial shockwave ring, debris droplets rain down.
6. The letters keep a subtle jelly wobble; one bead stretches and drips from a letter, hits the floor with concentric ripples, the tagline fades in with the ripple; hold the final frame ~2 s.
- Rhythm: each action 0.75–1.5 s; every bounce/settle uses an underdamped spring (2–3 light overshoots); falls use accelerating curves. Smooth 60fps feel, no stepped animation.

**Implementation hints**
- Preferred: WebGL fragment-shader raymarching. Spheres/capsules as SDFs fused with smin; normals drive fresnel + Blinn specular; the floor uses a reflection ray with distance blur. Title via MSDF/SDF text extruded and rounded/inflated.
- Drive every position and radius from the frame number (in Remotion pass useCurrentFrame into uniforms) for deterministic renders.
- Cheap fallback: SVG goo filter (feGaussianBlur + feColorMatrix alpha threshold) for the sticky merges, layered with radial gradients and white highlights.

**Do / Don't**
- Do: squash & stretch, stringing and reflections on every contact; rotate colors only within the four liquid hues.
- Don't: flat vector droplets, hard outlines, cold blue/cyan water, linear motion or hard cuts.
