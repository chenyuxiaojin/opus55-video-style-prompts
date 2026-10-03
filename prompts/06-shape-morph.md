# 06 · 形变动画 / Shape Morph

> 一个形状连续变身讲完整个故事,色块大胆、扁平如剪纸

## 中文提示词

# 风格:形变动画(Shape Morph)

做一条 16:9、约 10 秒的动画,主题是 {主题}。核心规则:全片只有**一个主形状**,不切镜、不消失,连续变成下一个形状——每次变形是一个故事节拍,形状本身就是叙事。

## 视觉语言
- 极简扁平图标:实心填充 + 圆头粗线(stroke-linecap: round),无描边、无渐变、无写实阴影。所有形状居中,约占画面高度 1/4~1/3,四周大量留白。
- 立体感只靠**折纸面**:叠一块深一档(或半透明白)的三角面,像纸折了一下。
- 配色只用 5 色:米白纸 #F2EEE3、墨黑 #17161C、番茄红 #EC3F2E、明黄 #F4BA2E、钴蓝 #272EDE。每个节拍是「一个整屏底色 + 一个对比色形状」,如红底白形、黄底红形;可用水平线把画面切成上下两块色。
- 质感:纸底和浅色形状叠一层很淡的纸纹噪点,画面四角轻微暗角。

## 字体排印
- 左下角固定章节角标:等宽数字 `01/07`(总数变灰)+ 粗黑体中文短词 {节拍名} + 极小字距拉宽的英文大写副标。右下角一排小圆点进度,当前项拉长成短胶囊。角标随底色黑白切换,换时上滑 + 竖向模糊淡入。
- 片尾:深底上一个圆润几何无衬线小写粗体 {标题文字},后面跟一个红色圆点句点;下方小号中文 {副标题} 字间加宽、中间用红点分隔,再下一行等宽英文全大写小字。

## 动效语言
- 节拍:每 1~1.5 秒一次变形;变形本身约 0.4~0.6 秒,稳定停留约 0.5 秒。
- 变形一律经过「圆/椭圆」中转:旧形状先收成一个圆点,再长成新形状。圆是所有形状之间的公共母体。
- 缓动:变形用 ease-in-out 偏快出慢收,落定时 5~10% 的回弹;运动中形状要压扁拉伸(下落拉长、拐弯压扁)并带方向性运动模糊,略微旋转倾斜。
- 附件(光芒、热气、波纹线等短线条)从主形状里弹出或缩回,彼此错开 40~60ms。
- **换底色转场**:新底色以形状为圆心,画一个边缘柔化的圆形向外扩张盖满全屏;或者地平线色块整体上推/下压换场。不用硬切、不用淡入淡出。
- 停留时保持微动:心跳式缩放 1.0→1.06、落点处椭圆波纹一圈圈向外散开、虚线轨迹描边跟随飞行路径。
- 收尾:圆点分裂成几个小球,飞成字母依次弹出;各节拍的颜色化成小色条沿弧线飞进句点;句点再泛出几圈彩色同心圆环淡出。

## 实现提示
- SVG path 插值:用 flubber 或 GSAP MorphSVG 在形状之间插值,所有形状路径预先重采样成相同点数并对齐起点,避免翻转。
- 运动模糊:Remotion 用 @remotion/motion-blur 的 CameraMotionBlur,或 SVG feGaussianBlur 按速度只做单向模糊。
- 圆形扩散换底:CSS clip-path: circle(r at x y) 动画 r,外加 filter: blur 柔边;或 SVG mask 里画一个模糊圆。
- 纸纹:SVG feTurbulence + 低透明度 multiply 铺满。

## 该做 / 不该做
- 该做:一形到底;每拍只说一件事;5 色轮换;形状居中。
- 不该做:多个并列主体;硬切或交叉淡化;写实渐变/3D/描边;大段文字。

## English Prompt

# Style: Shape Morph

Make a 16:9, ~10-second animation about {topic}. Core rule: the whole piece has **one hero shape** that never cuts away or disappears — it continuously turns into the next shape, and each morph is one story beat. The shape itself is the narrative; text does not carry the story.

## Visual language
- Minimal flat icons: solid fills plus thick round-capped strokes (stroke-linecap: round); no outlines, no gradients, no realistic shadows. Everything centered, the shape about 1/4–1/3 of frame height, generous empty space.
- Only one depth trick: a **paper-fold facet** — overlay a triangle one shade darker (or semi-transparent white) on the shape, as if the paper were creased.
- Five colors only: paper cream #F2EEE3, ink #17161C, tomato red #EC3F2E, sunny yellow #F4BA2E, cobalt blue #272EDE. Each beat is "one full-screen background + one contrasting shape" (white on red, red on yellow, white on blue). You may split the frame into two color bands with a horizontal line (horizon split).
- Texture: a very faint paper-grain noise over the cream background and light shapes, plus a subtle corner vignette.

## Typography
- Fixed chapter tag bottom-left: monospace counter `01/07` (total greyed) + a bold sans short word {beat name} + a tiny, widely tracked uppercase English subtitle. Bottom-right: a row of small progress dots, the active one stretched into a short pill. Tag color flips between black and white with the background; on change it slides up and fades in with vertical blur.
- End card: on a dark background, a rounded geometric sans, bold lowercase {title text} followed by a red dot as the period; below it a small, widely spaced {subtitle} split by a red dot, and one line of tiny uppercase monospace English.

## Motion language
- Rhythm: one morph every 1–1.5 s; the morph itself ~0.4–0.6 s, then ~0.5 s of settled hold.
- Every morph passes through a circle/ellipse: the old shape collapses into a dot, then grows into the new shape. The circle is the common parent of all shapes.
- Easing: ease-in-out with a quick start and slow landing, 5–10% overshoot on settle; squash and stretch while moving (stretch when falling, squash on turns), directional motion blur, slight rotation/tilt.
- Accessory strokes (rays, steam, ripple lines) pop out of or retract into the hero shape, staggered 40–60 ms.
- **Background-change transition**: the new background color expands from the shape's center as a soft-edged circle until it fills the screen; or the horizon color band pushes up/down to swap. No hard cuts, no crossfades.
- Keep holds alive: heartbeat scale 1.0→1.06, elliptical ripples spreading from a landing point, a dashed trail drawing along the flight path.
- Finale: the dot splits into a few small balls that pop into letters one by one; small color chips (one per beat color) fly along an arc into the period; the period emits a few colored concentric rings that fade out.

## Implementation hints
- SVG path interpolation: flubber or GSAP MorphSVG between shapes; resample all paths to the same point count and align start points to avoid flipping.
- Motion blur: in Remotion use CameraMotionBlur from @remotion/motion-blur, or a velocity-driven one-axis SVG feGaussianBlur.
- Circular reveal: animate the radius of CSS clip-path: circle(r at x y) with a filter: blur soft edge, or a blurred circle inside an SVG mask.
- Paper grain: SVG feTurbulence at low opacity, multiply blend, full-frame.

## Do / Don't
- Do: one shape from start to finish; one idea per beat; rotate within the five colors; keep the shape centered.
- Don't: several side-by-side subjects; hard cuts or crossfades between beats; realistic gradients, 3D or outlines; paragraphs of on-screen text.
