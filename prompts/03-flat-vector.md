# 03 · 扁平矢量 / Flat Vector

> 纯色几何满屏回弹,一颗珊瑚圆点串起全片

## 中文提示词

# 风格:扁平矢量 MG(一颗圆点一镜到底)

用代码(SVG + GSAP,或 Remotion)做一条约 10 秒、1920×1080 的扁平矢量动画,主题是 {主题},结尾落到 {品牌名}/{标题文字}。

## 视觉语言
- 纯色几何,零渐变、零投影、零描边光效。形状只用圆、圆角矩形、胶囊、三角、半圆拼。
- 体积只靠「双色平涂」:物体右侧切一条比本色暗约 10% 的色块,不画光影。
- 色板严格 6 色:电光蓝 #2B1EF4 主背景;珊瑚红 #F14B50 主角圆点;向日葵黄 #F8CA33;薄荷绿 #40FDAA;奶油白 #FDF7E9 地面/文字;墨蓝 #121434 只用于细节线和深色物件。远景用蓝的提亮版 #4B44F6 做剪影,再远就沉进背景。
- 细线只给小细节(眼镜、对勾、提示符号),线宽粗、圆头。点缀:放射短线、同心椭圆波纹、背景里半透明的圈/叉/胶囊。

## 字体排印
- 主标题:圆头几何超粗无衬线(Fredoka / Nunito Black 一类),奶油白,居中。
- 副标题:中文粗黑体 + 英文全大写小字,字距 0.3em,透明度约 70%。
- 分区标签贴角:「01 {标签}」小号数字 + 粗体词。

## 构图
- 正面平视,横向排布,地平线压在画面下 1/4~1/3。主体居中或三分点,四周留色块呼吸。
- 可用 2×2 等分色块网格做「并列要点」,每格一个大图标 + 角标。

## 动效语言
- 主角 = 一颗 {核心物件} 化身的珊瑚色圆点,贯穿全片:落地 → 变成场景元素 → 跳格 → 最后成为 {标题文字} 上的一个点。
- 全部弹性缓动:进场 back.out(1.7)/elastic.out(1,0.5),落地压扁拉伸(scaleY 0.6 / scaleX 1.3),再回弹。
- 元素从地面「长出」:scaleY 0→1,transform-origin 底部,stagger 0.06–0.1s。
- 快速位移加方向性运动模糊和两三条速度线。
- 节奏:每 0.25–0.5s 一个动作点,每个场景 1.5–2s 就换。
- 转场三招:① 镜头推进钻进画面里的小元素(下一场景缩在其中,配放射速度线 + 缩放模糊);② 珊瑚圆形遮罩扩散吞屏;③ 某一格面板放大铺满,其中的图形直接变成下一场景的元素。
- 结尾:标题字母逐个弹出,中文逐字下落回弹,圆点外扩一道细圆环脉冲,角落再弹出一个小 logo 标。

## 该做 / 不该做
- 做:一个主角贯穿到底,形状呼应(圆点 = 太阳 = 按钮 = 字母上的点)。
- 不做:渐变、写实阴影、细描边插画、多余字幕、线性匀速运动、超过 6 种颜色。

## English Prompt

# Style: Flat Vector Motion Graphics (one dot, one continuous take)

Build a ~10 s, 1920×1080 flat-vector animation in code (SVG + GSAP, or Remotion) about {topic}, ending on {brand_name}/{title_text}.

## Visual language
- Solid geometry only: no gradients, no drop shadows, no glow. Build everything from circles, rounded rects, capsules, triangles, half-circles.
- Volume comes only from two-tone flat fills: a strip on the right side ~10% darker than the base color. No lighting.
- Strict 6-color palette: electric blue #2B1EF4 (main background); coral #F14B50 (hero dot); sunflower #F8CA33; mint #40FDAA; cream #FDF7E9 (ground/type); ink navy #121434 (detail lines and dark objects only). Distant layers use a lifted blue #4B44F6 as silhouettes, fading into the background.
- Thin lines only for small details (glasses, check marks, alert glyphs): thick, round caps. Accents: radial burst ticks, concentric elliptical ripples, translucent circles/crosses/capsules floating in the background.

## Typography
- Headline: rounded geometric ultra-bold sans (Fredoka / Nunito Black family), cream, centered.
- Subline: bold Chinese sans + small all-caps English, letter-spacing 0.3em, ~70% opacity.
- Section labels pinned to corners: "01 {label}" with small numerals + bold word.

## Composition
- Frontal, eye-level, horizontal layouts; horizon sits in the lower 1/4–1/3. Subject centered or on thirds, generous color fields around it.
- A 2×2 grid of equal color panels works for parallel points: one big icon per panel + a corner label.

## Motion language
- Hero = a coral dot standing in for {core_object}, carried through the whole piece: it drops → becomes a scene element → hops panel to panel → ends as the dot on {title_text}.
- Everything springy: entrances back.out(1.7) / elastic.out(1,0.5); landings squash and stretch (scaleY 0.6 / scaleX 1.3) then rebound.
- Elements "grow" from the ground: scaleY 0→1, transform-origin bottom, stagger 0.06–0.1 s.
- Fast moves get directional motion blur plus two or three speed lines.
- Rhythm: an action beat every 0.25–0.5 s; each scene lasts 1.5–2 s.
- Three transitions: (1) camera pushes into a small element inside the frame (the next scene sits inside it) with radial speed lines + zoom blur; (2) coral circle mask expands to swallow the screen; (3) one panel scales up to fill the frame and its graphic morphs into the next scene's element.
- Ending: headline letters pop in one by one, Chinese characters drop in and bounce, a thin ring pulses out from the dot, a small logo mark pops in a corner.

## Do / Don't
- Do: one hero runs start to finish; shapes rhyme (dot = sun = button = letter dot).
- Don't: gradients, realistic shadows, fine-line illustration, extra captions, linear constant-speed motion, more than 6 colors.
