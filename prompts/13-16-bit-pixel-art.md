# 13 · 像素风 / 16-bit Pixel Art

> 320×180 低分屏里过完一整天,16 位游戏机开机即冒险

## 中文提示词

做一段约 10 秒的 16 位游戏机像素风动画,主题:{主题}。

**像素纪律**
- 在 320×180 小画布上按整数像素绘制,再最近邻整数倍放大(imageSmoothingEnabled=false / image-rendering: pixelated)。禁止抗锯齿、亚像素位移、模糊。
- 全片约 32 色。渐变 = 横向色带 + 带间 Bayer 棋盘格抖动;光束、光晕也用抖动点阵,不用透明度。

**画面**
- 横版卷轴,4–5 层视差:色带天空+像素云 → 亮暗两面的三角远山 → 中景树林剪影 → 地面 → 前景砖块。镜头匀速右移。
- {主角精灵} 16–24 像素高、大头身、2–4 帧走路;{可收集小物} 用宽度变化帧模拟旋转。
- 外罩 CRT:扫描线、圆角暗角、轻微桶形弯曲。

**字体**
- 左上 HUD:像素字 {计分标签} + 6 位补零金色数字;右上图标×计数,事件时跳增。
- 标题 {标题文字}:粗方块像素字,上黄下橙红分段填充 + 暗红硬投影;副标题放红色折角绶带上。
- 对话框:深蓝底、1px 浅描边、红底名牌、左侧头像格,文字逐字打出约 10 字/秒。

**动效时间轴**
1. 0–0.5s CRT 开机:黑屏亮点 → 过曝画面带一次纵向滚动错位后稳定。
2. 0.5–4s 跑跳拾取,头顶弹出分数上飘消失。
3. 4–6s 调色板轮换:同一场景按白天蓝→金→橙→洋红→夜紫→深靛分档硬切,每档约 0.75–1s,不插值;入夜出星点。
4. 6–7s 头顶「!/?」气泡,对话框先空框弹出再打字。
5. 7–7.5s 最近邻约 2 倍推近,硬切回全景。
6. 7.5–8.5s {核心物件} 爆出 6–8 道抖动点阵放射光束,小物上喷,角色周身蓝色抖动光晕。
7. 8.5–10s 标题先白闪一帧再落色;副标题逐字出现;底部 {按键提示} 每 0.5s 闪烁,其余待机微动。

**节奏**:坐标一律取整,精灵约 8–12fps 卡顿感;缓动只用线性或 steps(),不用弹性回弹。

**不要**:平滑渐变、圆滑矢量边、高斯辉光、现代无衬线字体、照片级配色。

## English Prompt

Create a ~10-second 16-bit console pixel-art animation about {topic}.

**Canvas & pixel discipline**
- Draw everything on a 320×180 internal canvas at integer pixel positions, then nearest-neighbor upscale by an integer factor to 1280×720 / 1920×1080 (canvas imageSmoothingEnabled=false, CSS image-rendering: pixelated). No sub-pixel motion, no anti-aliasing, no blur, no smooth gradients.
- Lock the whole piece to a ~32-color palette. Every gradient is horizontal color bands joined by 2–4px of Bayer/checkerboard dithering; light beams, glows and fades are ordered-dither stipple, never opacity.

**Visual language**
- Side-scrolling scene with 4–5 parallax layers: banded sky + pixel clouds → far mountains (triangular blocks, lit side / shadow side) → mid-ground tree line or building silhouettes → ground layer → foreground brick terrain. Each layer scrolls slower than the one in front; the camera pans right at a constant speed.
- {hero sprite} is ~16–24px tall with a big-head chibi ratio and a 2–4 frame walk cycle; {collectible} fakes rotation with a 1→3→5px-wide frame sequence.
- Wrap the frame in a CRT pass: a scanline every 2 physical pixels, rounded dark corners, slight barrel curve and edge bloom.

**Typography**
- Top-left HUD: pixel-font {score label} plus a 6-digit zero-padded counter in gold; top-right an icon × two-digit counter that ticks up on events.
- Title {title text} in chunky blocky pixel letters filled with stepped yellow-to-orange-red bands plus a 3–4px dark-red hard drop shadow; subtitle {subtitle} sits on a red ribbon banner with folded ends.
- Dialog box: deep navy fill, 1px light border, a red name tag {speaker} on the top-left corner, a 16×16 portrait slot on the left, typewriter text at ~10 chars/s, a small blinking triangle prompt bottom-right.

**Motion language (timeline)**
1. 0–0.5s CRT power-on: a bright dot on black → expands into a line → over-exposed picture with one vertical-roll glitch, then settles.
2. 0.5–4s scroll run: hero runs, jumps and picks things up; floating score numbers rise for 0.5s and vanish.
3. 4–6s palette cycling: the same scene hard-swaps through day blue → gold → orange → magenta → night violet → deep indigo, ~0.75–1s per step, no smooth interpolation; twinkling stars appear at night.
4. 6–7s story beat: a '!' or '?' bubble over the hero; dialog box pops in empty, then types.
5. 7–7.5s integer nearest-neighbor punch-in (~2×), then hard cut back to wide.
6. 7.5–8.5s climax: 6–8 dithered radial light beams burst from {core object}, small items spray upward, a blue dithered aura surrounds the hero.
7. 8.5–10s title slam: one solid white flash frame, then it settles into the gold-orange gradient; subtitle appears character by character; a bottom '{press prompt}' blinks every 0.5s while everything else idles (aura breathing, stars twinkling).

**Rhythm**: all movement steps by whole pixels; sprite animation at ~8–12fps for a chunky feel; scrolling may run at 60fps but coordinates are rounded. Easing is linear or stepped (steps()) only, never elastic or overshoot.

**Avoid**: smooth gradients, vector-smooth edges, Gaussian glow, half-pixel jitter, modern sans-serif fonts, photographic color beyond the 32-color palette.
