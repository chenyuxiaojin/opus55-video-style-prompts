# 04 · 线条动画(一笔画) / Line Art (One Continuous Line)

> 一根发光金线不断笔,在深蓝夜幕上从一点长成全景

## 中文提示词

## 风格:线条动画 · 一笔画(Line Art)
做一条约 10 秒、16:9 的动画,主题是 {主题}。整片只有一根线:从画外左侧进来,全程不断笔,从很小的 {起点意象} 画起,连成 {核心物件/整体场景},最后收成 {徽标形状} 并亮出 {标题文字}。线就是全部画面,留白同样重要。

### 视觉语言
- 背景:深海军蓝径向渐变,中心 #18233A,边缘压到 #070C14,重暗角;不放纹理和背景物件。
- 线:单一路径,细(1280 宽下约 2px),stroke-linecap/linejoin 全部 round。已画完的线是香槟金 #C9B27C;越靠近笔尖越亮越白(#FFF4D6),像金丝在冷却;外加极淡同色外发光。
- 笔尖:暖白光点 + 柔和光晕(约线宽 10 倍),是全画面最亮处。
- 形状语言:极简线稿。几何体用直角折线 + 半圆拱,自然物用叶形小环、S 曲线、回旋圈;各段用长水平基线或大弧线串起来。
- 唯一的实心块在收尾:{徽标形状} 先被线勾出轮廓,再瞬间灌满金色渐变(#E6D6A3 → #B4985E,左上亮右下暗),内部负形镂空。

### 字体排印
- 标题:古典罗马衬线全大写(Cinzel / Cormorant Garamond 一类),细到中等字重,字距约 0.5em,金色渐变填充,居中在线稿下方。
- 副标题:小号中文宋体/衬线,字距拉开,两侧各一条带圆点端头的短细线装饰。

### 构图
- 过程中笔尖保持在画面中心附近,地平线在下三分之一。
- 收尾全景:上徽标、中线稿、下标题居中定版,四周大量留白;线起点从画外淡入,终点一个小回勾。

### 动效语言
- 描边节奏不匀速:细节处(叶子、拱门、尖顶)画得慢,长直线和大弧线一冲而过。
- 镜头:2D 相机阻尼跟随笔尖,同时缓慢拉远让画面越来越完整;冲长直线时快速平移,带运动模糊残影。
- 高潮:徽标轮廓闭合 → 瞬间灌满金色 + 一两圈极淡光环外扩 → 全部线条降回统一香槟金。
- 收尾:镜头 ease-out 拉远上移腾出标题位;标题逐字淡入并由糊变清(stagger 40–60ms),副标题随后;最后静止 1.5–2 秒。
- 60fps 平滑,不用一拍二。

### 代码实现提示
- 整根线写成一条 SVG path,用 getTotalLength() + stroke-dasharray/stroke-dashoffset 驱动绘制进度;用 getPointAtLength(progress) 求笔尖坐标,放光点并作为相机目标。
- "越新越亮":同一路径再叠一层白色描边,只露末端 8–15%,加 blur。
- 相机 = 外层 <g> 的 translate/scale;Remotion 可用 CameraMotionBlur 做残影。
- 进度用分段关键帧(每个物件一段 easeInOut),不要线性。

### 该做 / 不该做
- 该做:一根线贯穿、留白充足、金色单一色相、光集中在笔尖。
- 不该做:多条独立线段、断笔、彩色、大面积填色、背景花纹、满屏粒子、粗或卡通描边。

## English Prompt

## Style: Line Art · One Continuous Line
Make a ~10-second 16:9 animation about {topic}. The whole film is a single line: it enters from off-screen left and never lifts or breaks. It starts as a tiny {origin motif}, keeps flowing into {core object / overall scene}, and finally resolves into a {emblem shape} that reveals {title text}. The line is the entire picture; negative space matters as much as the line.

### Visual language
- Background: deep navy radial gradient, center #18233A falling to #070C14 at the edges, with a strong vignette. No texture, grain or background objects.
- Line: one path, thin (~2px at 1280 wide), round linecap and linejoin everywhere. Settled line is champagne gold #C9B27C; the closer to the pen tip, the brighter and whiter it gets (#FFF4D6), like freshly heated gold wire cooling down. Add a very faint same-color outer glow.
- Pen tip: a warm-white dot plus a soft radial bloom (~10x line width) — the brightest thing on screen.
- Shape language: minimal line drawing. Geometry uses right-angle polylines and semicircular arches; organic forms use small leaf loops, S-curves and curls. Everything is traced by the same line on its way, linked by long horizontal baselines or big sweeping arcs.
- Only one solid element, at the end: the {emblem shape} is first outlined by the line, then instantly floods with a gold linear gradient (#E6D6A3 → #B4985E, light top-left to dark bottom-right, slight metallic sheen), with a negative-space cutout inside.

### Typography
- Title: classical Roman serif in all caps (Cinzel / Cormorant Garamond feel), light-to-regular weight, ~0.5em tracking, gold gradient fill, centered below the drawing.
- Subtitle: small CJK serif / Songti with wide tracking, flanked by two short hairlines with dot terminals.

### Composition
- During drawing the camera follows the pen tip and keeps it near frame center; the drawing's horizon sits in the lower third.
- Final wide shot: centered vertical lockup — emblem on top, line drawing in the middle, title below — with generous margins. Both ends of the line taper off gently (start fades in from off-screen, end finishes in a small hook).

### Motion language
- Drawing speed is not constant: slow on details (leaves, arches, spires), very fast on long straights and big arcs.
- Camera: a 2D camera tracks the pen tip with damped/lerp smoothing while slowly zooming out (scale shrinking) so the picture keeps growing; when the tip races along a long straight, the camera pans fast with visible motion-blur echoes.
- Climax: emblem outline closes → fills with gold within one frame + one or two very faint expanding halo ripples → all lines cool from glowing back to uniform champagne gold.
- Outro: camera eases out, pulling back and up to make room for the title; title letters fade in with blur-to-sharp, staggered ~40–60ms; subtitle follows; hold still for the final 1.5–2s.
- Smooth 60fps, no on-twos stepping.

### Implementation hints
- Write the whole line as ONE SVG path; drive drawing with getTotalLength() + stroke-dasharray/stroke-dashoffset; use getPointAtLength(progress) for the tip position, place the glow dot there and use it as the camera target.
- "Newest is brightest": overlay the same path again showing only the last 8–15% of the drawn length (via dasharray) in white with a blur filter.
- Camera = translate/scale on an outer <g>, damped-following the tip; in Remotion use CameraMotionBlur or multi-sample accumulation for the echo blur.
- Use a piecewise progress curve (one segment per object, each with easeInOut), never one linear ramp.

### Do / Don't
- Do: one line from start to end, lots of negative space, a single gold hue, light concentrated at the tip.
- Don't: multiple separate strokes, pen lifts, extra colors, heavy fills, background patterns, particle clutter, thick or cartoon outlines.
