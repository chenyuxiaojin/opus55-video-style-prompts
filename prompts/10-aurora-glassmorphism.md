# 10 · 弥散渐变玻璃拟态 / Aurora Glassmorphism

> 极光雾里浮起磨砂玻璃,一滴液态透镜收成品牌符号

## 中文提示词

# 风格:弥散渐变 + 玻璃拟态(Aurora Glassmorphism)

做一条约 10 秒、16:9、30fps 的产品发布感短片,主题是 {主题},主角是 {核心物件}(以若干块浮空 UI 玻璃卡片的形式出现),结尾落到 {标题文字} + {副标语}。

## 视觉语言
- 底:近黑紫 #060316 夜空,上面叠 3-4 团高斯模糊极大的弥散光斑——右上品红紫 #923DD6、中段靛紫 #6048DC、下方宝蓝 #404FF0、中心偏下青蓝 #6ECAF9,核心可亮到冰蓝 #C5ECFF。四周压暗角。光斑全程极慢漂移,不许出现硬边。
- 玻璃卡片:大圆角(画布宽的约 2%),填充白色 8-12% 透明,背景模糊 30-40px + 饱和度提高,1px 半透明白描边且上沿更亮,底部一层大而软的投影;卡片透出背后光斑的颜色,所以每张卡片自带紫→青的渐变。小胶囊按钮/气泡是更亮一级的半透明药丸。
- 一处发光点:卡片交界处放一颗青色小光球,带强泛光(bloom)。点缀极少量微小尘点。
- 多层卡片有前后层次,远层略暗略糊,做出浅景深。

## 字体排印
中性无衬线(SF Pro / Inter 气质),UI 文字 400-500 字重,白色,次要信息降到 50% 透明。收尾品牌字用细体(300)、字距略开、居中;副标语中英并排、小号、更淡。

## 构图
主卡片居中偏右,1-2 张小卡错层叠在左上/左下,形成对角线。收尾回到正中单行大字,四周全部留给光斑。

## 动效语言
- 缓动全部用柔和的 ease-out / 低回弹 spring,没有硬切、没有抖动,节奏松弛。
- 0-1s:卡片带 3D 透视倾斜(rotateX/Y 约 10-15°)从镜头前飘入,逐渐摆正。
- 1-5s:内容逐行出现——每行从左到右以“模糊+透明→清晰”的扫光方式显现;开关滑开、滑杆数值上涨;整体镜头缓慢推近并上移。
- 5-7s 招牌:从某个控件里拉出一滴液态玻璃(粘滞拉丝的 metaball),变成药丸形透镜,滑过文字时放大+折射+边缘轻微色散。
- 7-8s:其余卡片做焦外虚化并滑出画面,只有透镜保持清晰,带着镜头转到收尾。
- 8-10s:透镜缩小,恰好成为 {标题文字} 里一个圆形字母(或字标里的圆点),落定瞬间向外扩散一圈淡淡的冲击光环,副标语淡入。

## 实现提示
背景用 WebGL 片元着色器或多层 radial-gradient + filter: blur;卡片用 CSS backdrop-filter;透镜用 SVG feDisplacementMap 或着色器做折射与色散;景深用逐层 filter: blur 插值;Remotion 里全部由 frame 驱动,用 spring/interpolate,不依赖 CSS transition。

## 该做 / 不该做
该做:颜色只在冷色紫青区间流动;玻璃要“透出背景色”;一个视觉焦点贯穿全片。
不该做:纯白/灰色不透明卡片、硬阴影、霓虹描边、快速闪切、暖橙黄大色块、满屏粒子。

## English Prompt

# Style: Aurora Gradient + Glassmorphism

Make a ~10s, 16:9, 30fps product-launch style clip about {topic}. The hero is {core object}, shown as a few floating glass UI cards; it ends on {title text} + {tagline}.

## Visual language
- Background: near-black violet #060316 night, with 3-4 huge, heavily blurred gradient blobs — magenta-violet #923DD6 top-right, indigo #6048DC mid, royal blue #404FF0 low, cyan #6ECAF9 just below center, core reaching ice-blue #C5ECFF. Darkened vignette on all edges. Blobs drift very slowly; never any hard edge.
- Glass cards: large corner radius (~2% of canvas width), white fill at 8-12% opacity, backdrop blur 30-40px with boosted saturation, 1px translucent white border that is brighter on the top edge, one large soft drop shadow. Cards pick up the color of the blobs behind them, so each card carries its own violet→cyan gradient. Chips/bubbles are a brighter translucent pill.
- One glow accent: a small cyan light orb where two cards meet, with strong bloom. A few tiny dust specks, nothing more.
- Cards are layered front/back; rear layers slightly darker and softer for a shallow depth of field.

## Typography
Neutral sans (SF Pro / Inter feel). UI text weight 400-500, white, secondary info at ~50% opacity. The closing wordmark is thin (300), slightly open tracking, centered; the tagline sits below, small, bilingual side by side, dimmer.

## Composition
Main card center-right, 1-2 smaller cards staggered top-left / bottom-left on a diagonal. The ending returns to a single centered line, everything else left to the glow.

## Motion language
- All easing soft ease-out or low-bounce springs; no hard cuts, no jitter, relaxed pacing.
- 0-1s: cards float in toward camera with a 3D perspective tilt (rotateX/Y ~10-15°) and settle flat.
- 1-5s: content appears line by line, each line revealed left-to-right as a blur+fade → sharp sweep; a toggle slides on, a slider value climbs; the camera slowly pushes in and drifts up.
- 5-7s signature: a drop of liquid glass is pulled out of a control (gooey metaball stretch), becomes a pill-shaped lens, and glides over text, magnifying and refracting it with slight chromatic fringing at the edges.
- 7-8s: the other cards rack out of focus and slide off-frame; only the lens stays sharp and carries the camera to the ending.
- 8-10s: the lens shrinks and lands exactly as a round letter (or dot) in {title text}; on landing a faint shockwave ring expands outward and the tagline fades in.

## Implementation hints
Background: a WebGL fragment shader, or stacked radial-gradients + filter: blur. Cards: CSS backdrop-filter. Lens: SVG feDisplacementMap or a shader for refraction and dispersion. Depth of field: per-layer interpolated filter: blur. In Remotion drive everything from the frame with spring/interpolate, never CSS transitions.

## Do / Don't
Do: keep color flowing only within cool violet-cyan; glass must show the background color through it; keep one visual focal point running through the whole piece.
Don't: opaque white/gray cards, hard shadows, neon outlines, rapid flash cuts, large warm orange/yellow areas, screen-filling particles.
