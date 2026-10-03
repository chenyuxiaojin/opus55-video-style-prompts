# 07 · 贴纸风科普 / Sticker Explainer

> 白边贴纸拆解硬知识,一镜推过超长信息长图

## 中文提示词

# 贴纸风科普视频(16:9,约 10 秒,30fps)
主题:{主题};核心物件:{核心物件};标题:{标题文字};收尾数字:{核心数字}/{总数}。

## 视觉语言
- 背景冷浅灰 #EAEFF2,铺 24px 间距的淡点阵网格(点色约 #D3D9DE)。墨色 #2A3036,唯一强调色红 #EE4B3A,次级灰 #8E969D。红只给重点,面积 <10%。
- 所有实物用写实抠图(照片或 AI 生图去底),外加 6–10px 粗白描边 + 柔和下投影(0 8px 20px rgba(0,0,0,.15)),像贴纸;随机倾斜 -4°~4°,描边略不规则显手剪感。
- 信息单元做成圆角方块(圆角 6px):激活=墨色底白字,重点=红底白字,未激活=近白底浅灰字+极淡阴影;左上角可放小序号。
- 地图、图表用扁平 SVG:陆地 #C5CED3,重点区域墨色,路线为墨色弧线+红色枢纽点(外圈脉冲环)。

## 字体排印
- 中文用粗黑体(思源黑体 Heavy / HarmonyOS Sans Black),英文数字用几何无衬线特粗(Poppins / Montserrat ExtraBold)。
- 每段标题旁配全大写、字距 0.2em 的灰色英文小标;栏目头 = 红色小方块 + “01 栏目名”+ 英文。
- 巨型数字做主角,分母“/{总数}”用灰色细一号;关键词下加一道红色粗下划线。
- 常驻 HUD:左下品牌位(红方块+名称+字距英文),右下 4 段章节进度条,当前段红色填充随时间推进。

## 构图与运镜
- 全部内容排在一张竖向超长画布上,各段依次:标题+物件 → 物件拆解标注 → 数据网格 → 分类条形图 → 地图来源。相机平移/推近切段。
- 拆解段:物件居中,零件贴纸围一圈,引线从零件圆点拉出到右/左侧标签(中文粗标题+英文小标+数据小方块)。
- 结尾相机猛拉远,揭示整张长图其实是一块屏幕/卡片里的内容(粗白描边贴纸外框),画面背景翻成深炭灰 #1D272D;它偏左,右侧出巨大的红色数字(白描边)+一句总结+注脚,用红色虚点线把屏幕里的小数字连到大数字。

## 动效
- 节奏快而稳:每段 1.2–2 秒,段间转场 0.3–0.5 秒,easeInOutCubic,转场中给整画面方向性运动模糊。
- 标题逐行上浮淡入(间隔 0.2s),随后下划线 scaleX 0→1、副标与分隔线依次出现。
- 贴纸进场:从核心物件后方弹出飞到位,spring(damping≈14),带轻微旋转与过冲。
- 标签:引线 stroke-dashoffset 画出 → 文字淡入 → 数据方块 scale 0.6→1 依次弹出(stagger 60ms)。
- 数据方块从上一段“飞”进下一段的格子/条形图里(带旋转+模糊),当作数据的物理迁移;计数器 easeOutExpo 滚动到目标值,网格按列扫描点亮。
- 地图:贴纸弹入,虚线引线连到产地点,弧线路线逐段画出汇向红色枢纽,枢纽出脉冲环。
- 巨数字出场:scale 1.3→1 加红色光环扩散淡出。

## 实现提示
Remotion:一个 <AbsoluteFill> 里放超大 world 容器,用 interpolate 驱动 translate/scale 做相机;运动模糊用 @remotion/motion-blur 的 <CameraMotionBlur> 或转场段加 CSS filter: blur。贴纸白边:CSS drop-shadow 叠多层 0 0 0 白色,或 SVG feMorphology dilate + feFlood 白色。图表与地图全用 SVG。

## 该做 / 不该做
- 该做:知识点都落成看得见的物件或方块;一镜到底;数据跨段迁移。
- 不该做:渐变炫光、多强调色、细线插画、纯文字页、硬切。

## English Prompt

# Sticker Explainer video (16:9, ~10s, 30fps)
Topic: {topic}; hero object: {core_object}; title: {title_text}; closing stat: {key_number}/{total}.

## Visual language
- Background: cool light gray #EAEFF2 with a faint dot grid (24px spacing, dots ~#D3D9DE). Ink #2A3036, single accent red #EE4B3A, secondary gray #8E969D. Red marks only the answer/emphasis; keep red under ~10% of the frame.
- Every real object is a photoreal cutout (photo or AI image with background removed) with a thick 6–10px white outline plus a soft drop shadow (0 8px 20px rgba(0,0,0,.15)) — like a sticker stuck on paper. Random tilt of -4° to 4°; a slightly irregular outline reads as hand-cut.
- Data units are rounded tiles (6px radius): active = ink fill + white text, highlighted = red fill + white text, inactive = near-white fill + pale gray text + faint shadow; optional tiny index number top-left.
- Maps and charts are flat SVG: land #C5CED3, focus region in ink, routes as ink arcs converging on a red hub dot with a pulse ring.

## Typography
- Chinese: heavy black sans (Source Han Sans Heavy / HarmonyOS Sans Black). Latin & numerals: extra-bold geometric sans (Poppins / Montserrat ExtraBold).
- Every heading carries an ALL-CAPS gray English sub-label with 0.2em tracking. Section header = small red square + "01 Section" + English label.
- A giant number is the hero; the "/{total}" denominator is gray and smaller. Key words get a thick red underline drawn left to right.
- Persistent HUD: brand mark bottom-left (red square + name + tracked English), 4-segment chapter progress bar bottom-right, the active segment filling red over time.

## Composition & camera
- Lay all content on one tall super-canvas (like an infographic long-read): title + object → exploded object with callouts → data grid → category bar chart → source map. The camera pans/pushes across the canvas between sections; no hard cuts.
- Exploded section: object centered, part stickers around it, leader lines from a dot on each part to side labels (bold title + English sub-label + data tiles).
- Finale: the camera pulls way back to reveal the entire long canvas was content inside a screen/card (with a thick white sticker frame); the backdrop flips to dark charcoal #1D272D. The card sits left; on the right a huge red number with a white outline, a one-line summary and a footnote; a red dotted trail links the small number inside the card to the hero number.

## Motion
- Fast but steady: 1.2–2s per section, 0.3–0.5s transitions with easeInOutCubic and directional motion blur over the whole frame during moves.
- Title lines rise and fade in one by one (0.2s apart), then the underline scaleX 0→1, then subtitle and divider.
- Stickers burst out from behind the hero object and fly into place with a spring (damping ≈14), slight rotation and overshoot.
- Callouts: leader line draws via stroke-dashoffset → text fades in → data tiles pop scale 0.6→1 with 60ms stagger.
- Data tiles physically fly from one section into the next section's grid/bars (with rotation + blur) as data migration; counters roll up with easeOutExpo while the grid lights up in a column sweep.
- Map: stickers pop in, dashed leaders tie them to origin dots, arc routes draw segment by segment into the red hub, which emits a pulse ring.
- Hero number: scale 1.3→1 with an expanding red ring that fades out.

## Implementation hints
Remotion: put an oversized world container inside one <AbsoluteFill> and drive translate/scale with interpolate as the camera; motion blur via <CameraMotionBlur> from @remotion/motion-blur or CSS filter: blur during moves. White sticker edge: stacked CSS drop-shadow(0 0 0 white) or SVG feMorphology dilate + white feFlood. Charts and maps are pure SVG.

## Do / Don't
- Do: turn every fact into a visible object or tile; keep a one-continuous-shot feel; let the same data migrate between sections.
- Don't: gradient glows, multiple accent colors, thin-line illustration, text-only slides; no hard cuts, no red overload.
