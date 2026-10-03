# 12 · 复古 Synthwave / Retro Synthwave (80s Neon VHS)

> 霓虹网格奔向条纹落日,铬金大字砸在一盘老录像带上

## 中文提示词

# 复古 Synthwave(80s 霓虹 + VHS)风格提示词

把 {主题} 做成约 10 秒、1920×1080、30fps 的 80 年代 Synthwave 片头,整段像一盘 VHS 录像带在回放。

## 视觉
- Three.js 真 3D:黑色反光地板 + 洋红霓虹透视网格 #EC46E3,持续朝镜头滚动;地平线一条极亮品红光带。
- 正中巨大条纹落日:上近白黄 #F8FFAE → 橙 #DB7F3C → 下粉红 #E1306C,下半部被水平黑缝切成百叶,越往下缝越宽。
- 两侧低多边形线框山(青描边 #5BC8F0);天空近黑紫 #0B0311 → 深紫 #1E013A → 地平线洋红,带星点。
- {核心物件} 做黑剪影 + 一条红光带 #E50240;路边青白小光点;前景剪影可虚焦。所有亮部 bloom 溢光,地板有竖向长倒影。

## 字体
- 主标题 {标题文字}:超宽粗黑全大写几何无衬线,80s 铬金字——上天蓝 #81C6F6、中间近白高光线、下暖橙金,深紫挤出边。
- 副标题 {副标题}:斜体刷体手写,白芯 + 品红外发光 #EF58BA 的霓虹灯管字,斜压在主标题右下。
- 顶部小标语:超宽字距细体大写,两侧细横线。
- OSD:等宽像素白字,左上 PLAY ▶ / 结尾 STOP ■,右下 SP 时间码真实计时。

## 构图
一点透视、中轴对称:消失点 = 落日中心;地平线约在 55% 高度;标题三层锁版叠在落日上半部;低机位,轻微上下起伏与侧倾。

## 动效(约 10 秒)
1. 0–1.2s:4:3 小画幅 + 黑边、强噪点、底部 tracking 干扰带,出现 PLAY ▶,噪点退去后硬切满屏。
2. 1.2–4s:跟随 {核心物件} 匀速前进,网格滚动,偶发单帧水平撕裂。
3. ~4.2s:主标题从 3–4 倍大小带变焦模糊与重影砸入,0.25–0.5s 强 ease-out(expo.out)落定,四芒星光斑闪亮并约每秒在字母间跳一次;{核心物件} 拖光尾冲向地平线消失。
4. ~6.2s:副标题先以暗灯管出现,闪两下过曝后回落点亮。
5. ~7.5s:小标语淡入。
6. 9.3–10s:强 VHS 故障(切片错位 + RGB 分离),切 STOP ■。

## 代码提示
- 网格用 shader 的 fract(uv+time) 画线,EffectComposer + UnrealBloomPass;落日用 step(fract(y*N), 随 y 增大的阈值) 挖缝。
- 铬字:background-clip:text 多段渐变 + 多层 text-shadow 挤出;霓虹字多层品红 text-shadow,opacity 关键帧做通电闪烁。
- VHS 后期 shader:扫描线、噪点、色差、下移的 tracking 条、偶发 UV 水平切片位移、暗角 + 微桶形畸变。

## 该做 / 不该做
- 该做:只用洋红/紫/青/日落金四族色;所有光都 bloom;中轴对称。
- 不该做:扁平无光色块、现代细线 UI、干净无噪的画面、多个消失点。

## English Prompt

# Retro Synthwave (80s Neon + VHS Tape) Style Prompt

Turn {topic} into a ~10-second, 1920×1080, 30fps 1980s synthwave title sequence that plays like a VHS tape just pushed into a VCR.

## Visual language
- Scene: real 3D in WebGL/Three.js. An endless black reflective floor with a thin magenta neon perspective grid (emissive + bloom) that constantly scrolls toward camera to sell forward motion. A blazing magenta light band on the horizon.
- Dead center in the distance, a huge "striped sunset": near-white yellow #F8FFAE at top → gold #E0CD67 → orange #DB7F3C → pink #E1306C at bottom, the lower half sliced by horizontal dark gaps that get wider toward the bottom.
- Low-poly wireframe mountains on both sides (cyan edges #5BC8F0, deep purple fill #2A1655). Sky goes from near-black violet #0B0311 to deep purple #1E013A to horizon magenta #5E046D, with tiny stars.
- Midground: {core object} as a black silhouette / low-poly model with one saturated red light strip; a row of small roadside posts emitting cyan-white dots. Foreground silhouettes may be defocused for depth.
- Light: every bright element blooms (UnrealBloom); the floor shows long vertical reflections of neon and red lights.

## Typography
- Main title {title text}: ultra-wide, heavy, all-caps geometric sans (Bungee / Michroma / Orbitron Black type), rendered as 80s chrome: sky-blue #81C6F6 top → a near-white horizon highlight #FFFFFA → warm peach-gold #FDE8D3 / #CA7B74 bottom, with a deep purple extruded bevel and a thin bright outline.
- Subtitle {subtitle}: slanted brush script (Mr Dafoe / Kaushan Script type) as a neon tube: white core + magenta outer glow #EF58BA, tucked at the lower right of the main title, overlapping the sun.
- Top tagline {tagline}: very widely tracked all-caps thin sans, pale grey-white #BEBFD4, flanked by thin horizontal rules, center-dot separator.
- OSD corners: white monospaced pixel font — "PLAY ▶" top-left (ending with "STOP ■"), "SP 0:00:0X" bottom-right with a timecode that really counts seconds.

## Composition
- One-point perspective, strict center symmetry: vanishing point = sun center = frame axis; horizon at ~55% frame height.
- Title lockup sits over the upper half of the sun, three tiers top-down: small tagline → chrome title → neon script.
- Low, ground-hugging camera with a gentle breathing bob and slight roll.

## Motion and rhythm (~10 s)
1. 0–1.2s power-on: small 4:3 picture with black side pillars, heavy noise, desaturated, a tracking distortion band rolling at the bottom, "TRACKING" bottom-left, then "PLAY ▶" appears; noise clears within ~1s, then hard snap to full 16:9.
2. 1.2–4s cruise: camera follows {core object} at constant speed, grid scrolling, silhouettes passing, an occasional single-frame horizontal tear (sliced row offsets).
3. ~4.2s title slam: the chrome title drops from ~3–4× scale with radial/zoom blur and ghosting, settling in 0.25–0.5s on a hard ease-out (expo.out); on landing a four-point star lens glint flashes on a letter, then hops between letters about once per second as a sweep; meanwhile {core object} streaks to the horizon with light trails and vanishes.
4. ~6.2s script ignition: the subtitle first appears as an unlit dark tube, then flickers twice and overexposes before settling — like a neon sign powering on.
5. ~7.5s the top tagline fades in with its thin rules.
6. 9.3–10s ending: one strong VHS glitch (horizontal slice displacement + RGB split + broken text), top-left switches to "STOP ■".

## Signature techniques (code hints)
- Three.js: grid via GridHelper or a custom shader (fract(uv + time) lines); floor MeshStandardMaterial with low roughness + Reflector; EffectComposer with UnrealBloomPass.
- Sun: fragment shader with a vertical gradient; carve stripes with step(fract(y*N), threshold that grows with y).
- Chrome text: CSS background-clip:text multi-stop linear gradient (blue→white→pink→orange) + stacked text-shadows for extrusion; neon script with layered magenta text-shadow glow and opacity keyframes for the ignition flicker.
- VHS post: full-screen shader with scanlines, grain, chroma offset, a tracking band (high-noise strip drifting down), occasional horizontal UV slice offsets; light corner vignette + subtle barrel distortion.

## Do / Don't
- Do: limit color to magenta / purple / cyan / sunset gold; bloom every light; keep center symmetry; make the OSD timecode actually count.
- Don't: flat unlit colors, modern thin-line UI icons, a clean noise-free image, multiple vanishing points, or anything that breaks the 80s look.
