# 11 · 几何构成包豪斯 / Geometric Constructivist Bauhaus

> 原色基本形踩着节拍,在网格上一拍一拍搭成海报

## 中文提示词

用代码(Remotion/SVG/Canvas)做 10 秒 16:9 包豪斯动态海报,主题 {主题}。

## 视觉
- 暖象牙纸底 #F8F2E0,轻纸纹、四角微暗;铺极淡网格 #E7E0CE(1920 宽下 120px 模数),所有元素吸附网格。
- 只用纯平原色:红 #DC2F35、黄 #F5C60C、蓝 #2453A5、墨黑 #121013;无渐变、阴影、描边、圆角。
- 形状只用正圆、正方、三角、1/4 扇形、半圆、长条、小黑点,大小反差拉满。边缘加 1-2px 丝网毛边(feTurbulence+feDisplacementMap)。

## 版式
- 纸边当印刷框:四角裁切线、上下十字套准标;左上小字拍数「07 / 20」,右上刊头 {标题文字},左下一行技术说明,右下色票随新颜色出现逐格点亮。
- 一根细黑横轴 + 一根满高黑粗条切分画面,{核心物件} 用圆/三角/方块围着轴上小黑点咬合堆叠。
- 标题用粗重几何无衬线全大写,旋转 90° 竖贴左边;副标极小字号大字距,可双语。

## 动效
- 锁 120 BPM,每 0.5 秒一拍共 20 拍,每拍只做一个构造动作,拍数同步 +1。
- 0.15-0.25 秒 expo-out 冲到位后硬停,运动中带强方向模糊。
- 进场:画外滑入;长条 scaleX/Y 擦出;扇形旋转扫出;一拍内形变(方→扇)。落位前目标点闪十字准星。
- 开场:黑构造线从中心扫开后缩成淡网格,首个圆从上坠入。
- 中段:整组绕小黑点大幅旋转重组(约 1 秒)。
- 高潮:画面裂成网格瓷砖(Truchet 拼贴:扇形/三角/矩形)逐格旋转;再用单格翻牌(scaleX 1→0→1)切到整版黑底反相段,三原色形 + 小标签,形状切拼成字母形后翻回。
- 收尾:标题每拍蹦一个字母拼完,副标出现;只留一个小扇形持续旋转,其余定格。

## 不要
渐变、柔光、3D 透视、过度回弹、多元素同时乱动、三原色+黑以外的颜色。

## English Prompt

Build a ~10-second 16:9 "Geometric Constructivist Bauhaus" kinetic poster in code (Remotion / SVG / Canvas), about {topic}.

## Visual language
- Ground: warm ivory poster paper #F8F2E0 with very faint paper grain / vertical fibres and slightly darkened corners; overlay a very light grid #E7E0CE with a fixed module (120px at 1920 wide = 16x9 cells). Every element snaps to this grid in size and position.
- Flat primaries only: red #DC2F35, yellow #F5C60C, blue #2453A5, ink black #121013. No gradients, shadows, strokes or highlights.
- Basic shapes only: perfect circle, square, equilateral triangle, quarter-circle wedge, half circle, long bar, small black dot. Use extreme scale contrast (full-height bar vs tiny dot).
- Give fills a slight screen-print rough edge (SVG feTurbulence + feDisplacementMap, 1-2px), not perfect vectors.

## Layout
- Keep a paper margin as a print frame: corner crop marks, centre registration crosshairs top and bottom, tiny top-left beat counter "{beat label} 07 / 20", tiny top-right masthead {title text}, a one-line technical caption bottom-left, and colour swatch chips bottom-right that light up as each colour first appears.
- Composition is asymmetric but balanced: one thin black horizontal axis plus one full-height black bar slice the canvas; circle, triangle and squares interlock around a small dot on the axis, edges butting tightly.
- Type: heavy geometric sans (Archivo Black / Futura Bold feel), all caps, rotated 90 degrees running up the left edge; subtitles in tiny, widely tracked geometric light weight, optionally bilingual.

## Motion language
- Lock to 120 BPM: one beat every 0.5s, 20 beats total. Exactly one construction action per beat; the counter ticks with it.
- Moves are fast: 0.15-0.25s expo-out into place, then a dead stop for the rest of the beat - a "snap, hold, snap, hold" rhythm.
- Entrances: slide in from off-frame with strong directional motion blur; bars wipe in via scaleX/scaleY from one end; wedges sweep in by rotation like a fan opening; a shape can morph into another within one beat (square to quarter circle). Flash a crosshair at the target spot just before a shape lands.
- Open: a few black construction lines sweep out from centre and shrink into the faint grid; the first circle drops in from above.
- Mid: on one beat the whole group swings around the small dot as a pivot (~1s, rotational blur) and re-settles into a new composition.
- Climax: the canvas breaks into grid tiles, each filled with a quarter circle / triangle / bar (Truchet tiling), tiles rotate cell by cell; then per-cell card flips (scaleX 1-0-1) cut to a full black inverted section showing three primary shapes with small labels, the shapes slice and recombine into letter-like forms, then flip back.
- Ending: the title letters pop in one per beat to complete the vertical word, subtitle appears; only one small wedge keeps spinning, everything else freezes.

## Do / Don't
- Do: snap to grid, one action per beat, flat hard-edged colour, alternate generous negative space with full-bleed tiling.
- Don't: gradients, soft glow, rounded corners, 3D perspective, over-bouncy springs, many elements moving at once, any colour beyond the three primaries plus black.
