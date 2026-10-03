# 01 · 逐帧手绘 / Frame-by-Frame Hand-Drawn

> 纸上线条在沸腾,一拍二的卡通手作温度

## 中文提示词

# 风格:逐帧手绘(Frame-by-Frame Hand-Drawn)

用代码做一条约 10 秒、1920×1080 的 {主题} 动画,看起来像动画师在纸上一张张画出来的。

## 视觉语言
- 底:米黄纸 #ECE6CE + 细颗粒纸纹(噪点叠 multiply),整片不出现纯白和纯黑。
- 墨线:暖近黑 #1A120B,线宽随笔压粗细变化,尖头收笔,转角略过冲出头。
- 平涂只用三色:朱红 #D12F2C、明黄 #F2C429、奶白 #FFF9E3。色块与描线故意错位 3-6px(套色不准),边缘出头。
- 阴影不用渐变,用 45° 斜排线;主体背后放一块不规则水彩淡黄晕斑(#EDDA96,外圈更淡),边缘毛糙。
- {角色} 用橡皮管卡通:圆头白手套、细线手臂、两点黑眼 + 一笔高光,脸上可加红晕。

## 线条沸腾(招牌)
每张画都重算一遍路径:所有顶点加 1-3px 随机抖动,种子随「张数」变化,同一张保持不变。静止镜头也要轻微颤动,永远不完全静止。

## 帧率与节奏
- 以 24fps 为基准,默认一拍二(每张停 2 帧),快动作切一拍一,定格表情一拍三;实现:`drawIndex = floor(frame / hold)`,位置和抖动都只按 drawIndex 更新,禁止平滑插值。
- 动作用传统原画手法:预备—挤压拉伸—冲出—落地扬尘,配弧线动作轨迹(实线弧 + 红色点线弧)、速度线、旋转环线、汗滴/火星小符号。
- 镜头之间全硬切,机位在推近特写与稍远中景之间跳;冲击点插 1-2 张暖黑底星芒闪帧,接漫画爆炸(锯齿星芒 + 奶白云团 + 飞溅碎点)。

## 字幕排印
- {标题文字}:粗圆体中文、明黄填色 + 黑描边 + 向右下偏移的深色厚投影 + 一道白色高光,放在描边的波浪云形红徽章上;按笔画逐笔写出,笔尖带一颗小火花星。
- 英文副标:手写马克笔大写,奶白填 + 黑描边,逐字母蹦出;说明行用宽字距细黑体,中间用四角星分隔。
- 画面角落常驻手写场记 HUD(红色斜体):左上「SC. xx」,右下「on 2s / No. 0xx」张数计数,贴在半透明小纸签上,数字随张数跳。

## 结构建议
暗场预备(红线画在暖黑底上,椭圆聚光)→ 闪帧点亮切到纸面 → {角色} 表演 2-3 个动作 → 冲击闪帧 + 爆炸 → 标题逐笔写出 → 最后镜头拉远,揭示整张画其实是钉在定位尺上的动画纸(两长孔一圆孔、胶带、纸叠边),一支卡通手握铅笔在角落圈注「第 N 张」。

## 实现提示
Canvas 2D 或 SVG + Remotion:用 roughjs 或自写 jitter 路径;笔触用变宽 polygon;纸纹用预生成噪点图;所有随机值用 seeded random(frame→drawIndex),保证渲染确定。

## 不要
不要矢量光滑缓动、渐变、发光滤镜、投影模糊;不要 60fps 丝滑运动;不要超过三种填色;不要干净的几何直线。

## English Prompt

# Style: Frame-by-Frame Hand-Drawn

Build a ~10 s, 1920×1080 animation about {topic} in code that looks like an animator drew every sheet by hand.

## Visual language
- Ground: cream paper #ECE6CE with fine grain paper texture (noise on multiply). No pure white or pure black anywhere.
- Ink: warm near-black #1A120B, pressure-varying stroke width, tapered ends, corners that slightly overshoot.
- Flat fills from only three colors: vermilion #D12F2C, sunny yellow #F2C429, cream white #FFF9E3. Offset fills 3-6 px from the outline (misregistered print look).
- No gradient shading: use 45° hatching for shadows. Put an irregular watercolor-like pale-yellow glow blob (#EDDA96, lighter outer ring) behind the subject, ragged edges.
- {character} in rubber-hose cartoon style: round white gloves, thin-line arms, dot eyes with one highlight stroke, optional blush.

## Line boil (signature)
Redraw every drawing: jitter every vertex by 1-3 px with a seed tied to the drawing index, fixed within a drawing. Even held shots keep a subtle shimmer; nothing is ever perfectly still.

## Frame rate & timing
- 24 fps base. Default on twos (each drawing held 2 frames), switch to ones for fast action, threes for held expressions: `drawIndex = floor(frame / hold)`; update position and jitter only per drawIndex, never smooth-interpolate.
- Classic key-animation acting: anticipation, squash & stretch, smear, landing with dust puffs. Add motion arcs (solid ink arc + red dotted arc), speed lines, spin rings, little sweat/spark symbols.
- All shot changes are hard cuts, jumping between punchy close-ups and medium-wides. On impacts insert 1-2 warm-black starburst flash frames, then a comic explosion (jagged star burst, cream cloud puffs, flying debris).

## Typography
- {title}: heavy rounded Chinese/display font, yellow fill + black outline + thick dark drop shadow offset down-right + one white specular streak, sitting on an outlined scalloped cloud-shaped red badge. Write it on stroke by stroke with a tiny spark at the pen tip.
- English sub-title: hand-lettered marker caps, cream fill + black outline, popping in letter by letter. Caption line in wide-tracked thin sans, separated by a four-point star.
- A persistent handwritten production HUD in red italic: top-left "SC. xx", bottom-right "on 2s / No. 0xx" drawing counter on a small translucent paper tag, ticking with the drawings.

## Suggested structure
Dark anticipation (red line art on warm black, elliptical spotlight) → flash frame ignites to paper → {character} performs 2-3 actions → impact flash + explosion → title written on → final pull-back revealing the whole thing is an animation sheet on a peg bar (two slots and a round hole, tape, stacked paper edges) while a cartoon hand with a pencil circles "sheet No. N" in the corner.

## Implementation hints
Canvas 2D or SVG inside Remotion; roughjs or a custom jittered-path helper; variable-width strokes as polygons; a pre-baked noise image for paper; seeded random keyed on drawIndex for deterministic renders.

## Don't
No smooth vector easing, gradients, glow filters or blurred shadows; no 60 fps silkiness; no more than three fill colors; no clean geometric lines.
