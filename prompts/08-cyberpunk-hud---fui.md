# 08 · 赛博朋克 HUD / Cyberpunk HUD / FUI

> 电影级科幻界面：开机、扫描、锁定，冷青翻琥珀

## 中文提示词

做一段约 10 秒、16:9 的「电影科幻 HUD / FUI」动画，主题是 {主题}，画面中心是 {核心物件} 的全息线框，叙事走「开机 → 搜索 → 锁定」三幕。

## 视觉语言
- 背景近黑偏青 #030E10，叠极淡六边形网格、径向暗角和细扫描线；四角留 L 形取景框角标。
- 一切由 1–2px 细线构成：同心圆环、断续粗弧段、刻度尺、方位角数字（每 30°）、十字准星、角括号锁定框。不用实心大色块。
- 主色冷青 #3CE8DC，次级线 #1E8C88，读数用暖白 #F3F0E8。全部亮线加辉光（bloom），最亮处过曝成 #6EFFFC。
- 中心物件做成半透明全息体：经纬网格 + 发光轮廓线，内部有青色雾光，缓慢自转。

## 字体排印
- 标题/大数字：方正几何科技无衬线（Rajdhani / Oxanium / Orbitron 气质），粗体，等宽数字，单位小一号贴右下。
- 标签：等宽字体（Share Tech Mono / JetBrains Mono），全大写、字距加宽、8–11px，英文代号 + 中文小注并排。
- 中文大标题用黑体 Heavy。

## 构图
- 左右两列窄数据面板（系统日志、遥测条形、频谱柱、十六进制数据流、候选列表），中间 50% 宽留给大圆形瞄准镜 + {核心物件}。
- 顶部居中梯形状态胶囊显示阶段名 {状态文字}；右上 UTC 时钟 + REC 红点；底部横向刻度尺带游标。

## 动效语言
- 0–0.5s：CRT 开机——黑屏中一道横向光线张开成画面。
- 0.5–2.5s 开机：主环从小而亮扩成大而细（ease-out），描边顺时针画出；断续弧段、刻度、面板依次 stagger 进场；日志逐行打字带方块光标，行尾跳 [OK]。
- 2.5–6.5s 搜索：带渐隐拖尾的扇形扫描束顺时针转，约 2 秒一圈；大号距离数字持续递减；遥测条形弹性填充；中途一帧横向切片错位 + RGB 分离的 glitch；中心物件加速旋转后减速停到目标；四角 V 形箭头带残影向中心收拢，角括号框套住目标并跳出百分比。
- 6.5–7.5s 锁定（招牌）：一帧六边形蜂窝冲击波 + 放射速度线闪白；全局配色从青瞬间翻成琥珀 #FF8A1E；镜头猛推进（侧栏被推出画外并虚化），再回弹落定；横幅「{标题文字} / LOCKED」两端带斜纹警示块。
- 7.5–9.5s 保持：坐标逐字打出，数字以指数缓动收敛到终值，光标闪烁，小标记缓慢漂移，进度条走完显示完成。不要静止。
- 结尾 CRT 关机：画面压成横线再缩成一个亮点。
- 所有状态标签切换时先随机字符乱码再解码成正确文字。

## 实现提示
- Three.js：线框球 / EdgesGeometry + LineBasicMaterial，配 UnrealBloomPass；或 Canvas 2D 用 shadowBlur + globalCompositeOperation='lighter' 叠加。
- HUD 层用 SVG：stroke-dasharray 描边动画、rotate 环、conic-gradient 或扇形 path 做扫描束。
- 数字、乱码、打字效果全部由帧号确定性计算（Remotion 中用 useCurrentFrame + 固定种子随机）。
- 配色用 CSS 变量，锁定时整体 lerp 切换。

## 该做 / 不该做
- 该做：信息密度高但层级清晰；每个角落都有微动；辉光只给亮线。
- 不该做：圆角卡片、渐变大色块、可爱图标、柔和缓入缓出的慢节奏；不要满屏都是同等亮度。

## English Prompt

Create a ~10-second 16:9 "sci-fi movie HUD / FUI" animation about {topic}. The center is a holographic wireframe of {core object}; the story runs in three acts: Boot → Search → Lock.

## Visual language
- Background near-black teal #030E10, overlaid with a very faint hexagon grid, radial vignette and fine scanlines; L-shaped viewfinder corner marks.
- Everything is built from 1–2px thin lines: concentric rings, broken thick arc segments, tick scales, bearing numbers every 30°, crosshair reticle, corner-bracket lock box. No large solid color blocks.
- Primary cool cyan #3CE8DC, secondary lines #1E8C88, readouts in warm white #F3F0E8. Every bright line gets bloom; the hottest cores blow out to #6EFFFC.
- Render {core object} as a translucent hologram: lat/long grid + glowing outlines, cyan inner haze, slow self-rotation.

## Typography
- Titles / big numbers: squarish geometric tech sans (Rajdhani / Oxanium / Orbitron feel), bold, tabular figures, unit one size smaller at bottom-right.
- Labels: monospace (Share Tech Mono / JetBrains Mono), all caps, wide tracking, 8–11px, English code + small CJK/secondary note side by side.
- Big CJK headline in a heavy gothic sans.

## Composition
- Two narrow data columns left and right (system log, telemetry bars, spectrum bars, hex data stream, candidate list); the middle ~50% width holds a large circular scope + {core object}.
- Top-center trapezoid status pill shows the phase name {status text}; top-right UTC clock + red REC dot; bottom horizontal ruler with a cursor.

## Motion language
- 0–0.5s: CRT power-on — a horizontal light line opens into the picture on black.
- 0.5–2.5s Boot: main ring expands from small/bright to large/thin (ease-out) and strokes on clockwise; arc segments, ticks and panels stagger in; log types line by line with a block cursor, each line ends with [OK].
- 2.5–6.5s Search: a wedge radar sweep with a fading trail rotates clockwise, ~2s per turn; a big distance number keeps counting down; telemetry bars fill with overshoot; one frame of horizontal slice displacement + RGB split glitch; {core object} spins fast then decelerates onto the target; V-chevrons with echo trails converge from the corners and a corner-bracket box snaps onto the target with a percentage.
- 6.5–7.5s Lock (signature): a one-frame hex-cell shockwave + radial speed lines flash; the whole palette flips instantly from cyan to amber #FF8A1E; camera punches in hard (side panels pushed off-frame and defocused), then springs back and settles; banner "{title text} / LOCKED" with diagonal hazard-stripe end caps.
- 7.5–9.5s Hold: coordinates type out character by character, numbers converge to final values with exponential ease, cursor blinks, small markers drift, a progress bar completes. Never fully static.
- End with CRT power-off: frame collapses to a line, then to a bright dot.
- Every status label change first scrambles through random glyphs, then decodes into the right text.

## Implementation hints
- Three.js: wireframe sphere / EdgesGeometry + LineBasicMaterial with UnrealBloomPass; or Canvas 2D with shadowBlur + globalCompositeOperation='lighter'.
- HUD layer in SVG: stroke-dasharray draw-on, rotating rings, conic-gradient or wedge path for the sweep.
- Numbers, scramble and typing all computed deterministically from the frame number (in Remotion: useCurrentFrame + seeded random).
- Drive colors with CSS variables and lerp the whole theme at lock.

## Do / Don't
- Do: high information density with a clear hierarchy; micro-motion in every corner; bloom only on bright lines.
- Don't: rounded cards, big gradient fills, cute icons, soft slow ease-in-out pacing; don't make everything equally bright.
