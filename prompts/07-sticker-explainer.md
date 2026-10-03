# 07 · 贴纸风科普 / Sticker Explainer

> 白描边贴纸,一镜推到底的长画布科普

## 中文提示词

风格:贴纸风科普,一张超长画布,镜头一路推下去。
画面:浅灰点阵底#EAEFF2,墨#26313A,红#EE4A3C点重点,收尾转深底#1F2A31;抠图套粗白描边+软投影;数据用墨色圆角小方块。
字体:粗黑体标题+宽字距英文小副标,关键词下红条划出;角落固定章节进度条。
动效:30fps;换章镜头0.5s急推+强运动模糊;同批方块错峰飞向新布局,旋转落定;元素5帧弹出微过冲;数字滚动。收尾拉远,画布缩进白边容器,关键数字贴纸弹出。
实现:Remotion超高画布+camera;方块同key做FLIP变形;多帧采样运动模糊;SVG feMorphology描边。
不要:硬切/淡入换页;无描边扁平图标;多色;匀速漂移。
内容:{在这里写你的内容}

## English Prompt

Style: sticker explainer — one extra-tall canvas, the camera keeps pushing down through it.
Look: light gray dot-grid bg #EAEFF2, ink #26313A, red #EE4A3C for emphasis only, finale on dark #1F2A31; cutouts get a thick white sticker outline + soft shadow; data as small rounded ink chips.
Type: heavy sans headlines + wide-tracked small English subtitle; red marker bar wipes under key words; fixed corner chapter progress bar.
Motion: smooth 30fps; chapter change = 0.5s fast camera push with strong directional motion blur; the same chips fly staggered into each new layout and settle with rotation; elements pop in ~5 frames with slight overshoot; numbers count up. Finale pulls back: whole canvas shrinks into a white-outlined container, key number pops out as a sticker.
Build: Remotion tall canvas + camera transform; same-key chips FLIP between layouts; multi-sample motion blur; SVG feMorphology outline.
Avoid: hard cuts/fades between pages; flat outline-less icons; many colors; constant-speed drifting camera.
Content: {your content here}
