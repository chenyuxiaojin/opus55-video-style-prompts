# 15 · 综艺花字 / Variety Show Captions

> 多层描边糖果花字砸上真实素材,把情绪放大十倍

## 中文提示词

## 风格:综艺花字(Variety Show Captions)

做一条 9:16 竖屏、约 8-10 秒的短片,主题是 {主题}。底层是真实照片/视频素材 {主体素材},上层用代码叠「综艺后期花字」,专门把情绪放大。分 3-4 段,每段一种情绪(如 惬意/尴尬/登场/震惊),各配一套颜色和贴纸。

### 视觉语言
- 底素材全画幅铺满,每段做缓慢推近(scale 1.0→1.08),段内可再来一次 0.5 秒急推(crash zoom)制造紧张。
- 配色:柠檬黄 #FFE24A→琥珀 #F5B93A 渐变字、热粉 #F0257F、青蓝 #3ED8F0、警示红 #E5144A,所有元素最外层一律深靛蓝 #1E2266 硬描边。暖情绪用黄+粉,冷/尴尬情绪用青蓝+白,高潮用红+黄。
- 形状:圆角胶囊、带小三角耳朵的标题牌、斜切丝带、四角星闪光、问号/汗滴贴纸、警示斜纹条、漫画爆炸星。饱满糖果感扁平矢量。

### 字体排印
- 圆润特粗黑体(站酷快乐体 / 庞门正道粗书体 / 思源黑体 Heavy 方向),字重 900。
- 花字=「渐变填充 + 白色内描边 + 彩色外描边 + 深色硬投影(向下偏移 4-6px 无模糊)+ 外发光」至少 4 层。
- 字号故意不统一:关键字放大 1.2-1.4 倍、单字上下错落、整行轻微倾斜 -4°~-8°。
- 旁白/内心戏用小号白字+深色阴影,前面加 (小声) 之类括号标注;冷场时用竖排单列字。

### 构图
- 主花字放下 1/3 居中;标题角标左上;内心戏小字左上空白处;人物/主体的「名牌」放主体身侧(小胶囊头衔 + 大名字 + 斜丝带副标三层叠)。
- 高潮段切成漫画版:放射条纹满屏背景 + 主体抠像(白色锯齿撕纸边+深色描边)+ 下方爆炸星托住大字,四周加「惊吓抖动线」。

### 动效语言
- 一切进场都用过冲弹簧(Remotion spring,damping≈8-10,stiffness≈180),scale 0→1.15→1,带 2-4 帧运动模糊。
- 主花字逐字弹出,每字间隔约 3 帧,字落位后轻微呼吸缩放;四角星闪光随机闪烁。
- 内心戏字用打字机逐字出现(约 8 字/秒);进度类小图标逐格填充。
- 问号贴纸依次蹦出并飘动;汗滴滑落。
- 名牌按 头衔→名字→丝带 依次从侧面滑入弹定;警示条弹出后红/粉两色交替闪烁(约 4Hz)。
- 高潮:硬切到漫画版,爆炸星带旋转弹入,大字第一个字从大砸下、后面字依次追上;顶部再掉下一个仪表/计量贴纸,指针甩到最大。
- 段间转场:斜向三色条纹(青/黄/粉,带白条纹底)整屏扫过,中间闪一下节目标题牌,全程带横向动态模糊,约 0.3 秒。

### 实现提示
Remotion + DOM/SVG:花字用 `-webkit-text-stroke` 叠多层(或多个绝对定位副本逐层加粗描边)+ `background-clip:text` 渐变 + `text-shadow` 硬投影;爆炸星/撕纸边/放射条纹用 SVG polygon 程序生成(随机半径锯齿);放射背景用 `repeating-conic-gradient`;运动模糊用按速度变化的 `filter: blur()` 或方向性重影。

### 该做 / 不该做
- 该做:每段只放大一种情绪;层层描边要厚;节奏密,1-2 秒必有新元素进场。
- 不该做:细字重、单层描边、低饱和、线性缓动、挡住主体脸。

## English Prompt

## Style: Variety Show Captions

Make a 9:16 vertical clip, ~8-10 s, about {topic}. The base layer is real photo/video footage {subject_footage}; on top, code-driven "variety-show post-production captions" that exaggerate emotion. Split into 3-4 beats, one emotion each (e.g. cozy / awkward / grand entrance / shock), each beat with its own color set and sticker kit.

### Visual language
- Footage fills the frame with a slow push-in per beat (scale 1.0→1.08); optionally one 0.5 s crash zoom inside a beat to build tension.
- Colors: lemon #FFE24A → amber #F5B93A gradient text, hot pink #F0257F, cyan #3ED8F0, alert red #E5144A; every element gets an outermost hard outline in deep indigo #1E2266. Warm emotions = yellow + pink, cold/awkward = cyan + white, climax = red + yellow.
- Shapes: rounded pills, title plate with little triangle ears, slanted ribbons, four-point sparkles, question-mark / sweat-drop stickers, hazard-stripe banners, comic explosion stars. Plump candy-like flat vectors, no realistic lighting.

### Typography
- Rounded ultra-bold CJK/Latin display face (ZCOOL KuaiLe / heavy rounded gothic / Source Han Sans Heavy direction), weight 900.
- A caption = at least 4 layers: gradient fill + white inner stroke + colored outer stroke + dark hard drop shadow (4-6 px down, no blur) + soft outer glow.
- Deliberately uneven sizing: key glyph 1.2-1.4× larger, glyphs bob up/down, whole line tilted -4° to -8°.
- Inner monologue: small white text with dark shadow, prefixed by a bracketed whisper tag; awkward silence = a single vertical column of text.

### Composition
- Main caption centered in the lower third; show badge top-left; monologue in top-left negative space; a subject "name tag" beside the subject (small pill title + big name + slanted ribbon subtitle, stacked).
- Climax cuts to a comic version: full-screen radial sunburst stripes + subject cutout (white jagged torn-paper edge + dark outline) + an explosion star holding the big word, with shake/emanata lines around.

### Motion language
- Every entrance is an overshooting spring (Remotion spring, damping ≈8-10, stiffness ≈180), scale 0→1.15→1, with 2-4 frames of motion blur.
- Main caption pops in per glyph, ~3 frames apart, then breathes gently; sparkles twinkle randomly.
- Monologue text types on (~8 chars/s); progress-style icons fill cell by cell.
- Question-mark stickers pop in sequentially and float; sweat drops slide down.
- Name tag slides in from the side in order title → name → ribbon; the alert banner pops in then flashes red/pink (~4 Hz).
- Climax: hard cut to comic layout, explosion star spins in, the first glyph slams down huge and the rest catch up; a gauge/meter sticker drops from the top and its needle whips to max.
- Beat transitions: a diagonal tri-color stripe wipe (cyan/yellow/pink over white pinstripes) sweeps the screen with the show badge flashing mid-wipe, heavy horizontal motion blur, ~0.3 s.

### Implementation hints
Remotion + DOM/SVG: stack multiple `-webkit-text-stroke` layers (or absolutely positioned copies with increasing stroke) + `background-clip:text` gradients + hard `text-shadow`; generate explosion stars / torn edges / rays as SVG polygons with randomized radii; sunburst via `repeating-conic-gradient`; motion blur via velocity-driven `filter: blur()` or directional ghost copies.

### Do / Don't
- Do: amplify exactly one emotion per beat; make outlines thick and layered; keep it dense — something new enters every 1-2 s.
- Don't: thin weights, single-layer strokes, desaturated palettes, slow linear easing, or clutter that covers the subject's face.
