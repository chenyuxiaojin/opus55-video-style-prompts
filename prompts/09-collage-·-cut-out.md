# 09 · 拼贴剪贴 / Collage · Cut-out

> 牛皮纸上剪报网点拼贴,12fps 手工步进逐层贴满

## 中文提示词

# 风格:拼贴剪贴(Collage · Cut-out)
用代码做一条约 10 秒的复古剪报拼贴动画,主题是 {主题}。像在牛皮纸桌上现场拼一张杂志封面,每样东西都是剪下来贴上去的纸片。

## 视觉语言
- 底:牛皮纸 #90785B,带细颗粒噪点 + 明显暗角(四角压到约 #745F49);结尾可整版换成报刊红 #BA171F(边缘暗到 #871015)。
- 主色只有四个:牛皮棕、报刊红 #A11319~#BA171F、近黑墨 #171209、旧纸米白 #D9D1BA。彩色只来自后贴入的彩印素材,同样盖网点。
- 所有图片都做成半调网点印刷:黑白高反差 + 圆点网屏;沿主体轮廓抠图,外圈留 4–6px 米白纸边 + 柔和投影,像真剪下来的。
- 纸片边缘不规则:撕边(锯齿 + 白色纤维边)、剪刀直边混用;报纸碎片满是小号旧铅字栏。
- 配件:半透明牛皮胶带、黄铜图钉、虚线剪裁线 + 小剪刀、编号贴标、圆形贴纸徽章。

## 字体排印
- 标题:超粗压缩无衬线(Anton / Bebas 类),全大写,黑字放在撕边白胶带上,或白字压在斜放黑色横幅上(横幅下沿配一条红边)。
- 中文大字:粗黑体,一字一块方纸(红底黑字、白底黑字、黑底白字、白底红字轮换),像勒索信拼字。
- 拟声词:每个字母贴在不同颜色的小纸片上,高低错落、各自倾斜。
- 角落元信息:小号等宽字体、大写、宽字距(如"{刊名} — N°{期号} — {季节}"),压得很淡。

## 构图
- 中心一个抠图主体 {核心物件},背后叠一个大红圆;报纸碎片贴在左右边缘、部分出画;标签与气泡围着主体。
- 所有纸片轻微旋转 ±2–8°,绝不横平竖直对齐;层层叠压,允许出血。

## 动效
- 逐格步进:整体按 12fps 走(每 2 帧才更新一次),每一步所有纸片都随机抖 1–3px、±0.5° 的"手工抖动"。
- 进场方式:从画外滑入后停住、比例弹出(轻微过冲)、像盖章一样砸下;节奏是每 0.25–0.5 秒一个新动作,逐个叠加,不同时出现。
- 招牌叙事动作:主体上出现虚线 → 剪刀沿线走约 1 秒 → 裂口变红 → 被剪开的部分翻飞出去,炸出拟声词和纸屑 → 里面的 {隐喻世界} 被撕开露出,再逐个弹出小贴纸。
- 主体可做"剪纸木偶"动作:下巴等局部作为单独纸片绕铰点开合。
- 转场:整页像纸一样卷起撕走(卷边带高光阴影),露出下一层纸;收尾是 {标题文字} 胶带条砸入 + 副标题 + 圆形贴纸,停住约 1 秒。

## 实现提示
- Remotion / Canvas:用 `Math.floor(frame/2)*2` 量化时间;抖动用以步数为种子的伪随机。
- 网点:SVG pattern 圆点 + mask,或 Canvas 按亮度画圆点;撕边用 SVG clipPath 加随机锯齿路径。
- 纸边:`filter: drop-shadow` 叠一圈白色描边;颗粒用 feTurbulence 叠 multiply。
- 卷页转场:clip 一个移动的斜切面 + 卷筒高光渐变。

## 该做 / 不该做
- 该做:一切像纸;红黑米白强对比;逐步叠满画面。
- 不该做:光滑渐变、发光、毛玻璃、平滑 60fps 补间、整齐网格排版、纯矢量扁平插画。

## English Prompt

# Style: Collage · Cut-out
Code a ~10-second retro newspaper-collage animation about {topic}. It should feel like someone assembling a magazine cover live on a kraft-paper desk with scissors, tape and pins — every element is a piece of paper that was cut out and stuck down.

## Visual language
- Ground: kraft paper #90785B with fine grain noise and a strong vignette (corners down to ~#745F49). The finale may swap to a full newsprint-red #BA171F (edges ~#871015).
- Only four main colors: kraft brown, press red #A11319–#BA171F, near-black ink #171209, aged off-white paper #D9D1BA. The only other color comes from pasted-in color-print clippings (nebula, botanicals, stickers), which are also halftoned.
- Every image is halftone print: high-contrast B&W with a round-dot screen, cut along the subject's silhouette, with a 4–6px off-white paper border and a soft drop shadow.
- Edges are irregular: torn edges (jagged with white fiber rim) mixed with straight scissor cuts; newspaper scraps are dense columns of tiny old type.
- Props: translucent masking tape, brass pushpins, dashed cut lines with a small scissors icon, number tags, round sticker badges.

## Typography
- Headlines: ultra-bold condensed sans (Anton / Bebas type), all caps, black on a torn white tape strip, or white on a tilted black banner with a red lower edge.
- Big CJK/display characters: one glyph per square paper chip, alternating red/black/white combos, ransom-note style.
- Onomatopoeia: each letter on its own differently colored chip, staggered and individually rotated.
- Corner metadata: tiny monospace caps with wide tracking (e.g. "{publication} — N°{issue} — {season}"), low contrast.

## Composition
- One cut-out hero {core object} in the center, a big red disc behind it; newspaper scraps pinned at the left/right edges and bleeding off-frame; tags and speech bubbles orbit the hero.
- Every piece is rotated ±2–8°, never grid-aligned; heavy overlapping, bleed allowed.

## Motion
- Stepped animation: the whole piece runs on 12fps (update every 2 frames), and on every step each paper piece jitters 1–3px and ±0.5° like hand-placed boil.
- Entrances: slide in from off-frame and stop, scale pop with slight overshoot, or slam down like a stamp. One new action every 0.25–0.5s, layering up one at a time.
- Signature beat: a dashed line appears on the hero → scissors travel along it for ~1s → the cut turns red → the cut-off part flips away with ransom-letter onomatopoeia and paper confetti → a torn opening reveals {metaphor world}, then small stickers pop in one by one.
- Paper-puppet acting: parts like a jaw are separate pieces rotating on a hinge point.
- Transition: the whole page curls up and tears away like paper (highlight + shadow on the curl), revealing the next layer; end with a {title text} tape strip slamming in, subtitle, round sticker, then hold ~1s.

## Implementation hints
- Remotion / Canvas: quantize time with `Math.floor(frame/2)*2`; seed jitter with the step index.
- Halftone: SVG dot pattern + mask, or Canvas dots sized by luminance; torn edges via SVG clipPath with randomized jagged paths.
- Paper border: white outline plus `filter: drop-shadow`; grain via feTurbulence in multiply.
- Page curl: clip with a moving diagonal edge plus a cylinder highlight gradient.

## Do / Don't
- Do: make everything feel like paper; hard red/black/off-white contrast; let the frame fill up gradually.
- Don't: smooth gradients, glows, glassmorphism, silky 60fps tweening, tidy grid layouts, flat vector illustration.
