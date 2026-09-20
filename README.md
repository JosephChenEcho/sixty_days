# sixty_days 六十天

A browser-based visual novel adapted from the original short story 《六十天》.
纯静态网页文字冒险游戏，直接用 GitHub Pages 部署，点开即玩。

## Play

https://doctorblaza.github.io/sixty_days/

## Structure

```
index.html          游戏入口
css/style.css       样式（水彩素描风，参考《水仙 Narcissu》）
js/engine.js        文字冒险引擎：打字机 / 分支选项 / 存档读档 / 背景切换
js/music.js         BGM 管理：按剧情阶段切换，淡入淡出
js/story.js         《六十天》完整剧本（序幕 + 八章 + 尾声）
assets/bg-*.jpg     场景插画（AI 生成，原创；女主的脸只在最后一幕出现）
assets/music/*.mp3  背景音乐（title / calm / tense / sad / end）
```

## 音乐署名 / Music credits

All background music composed by **Kevin MacLeod** (incompetech.com),
licensed under **CC-BY 3.0**: https://creativecommons.org/licenses/by/3.0/

| 文件 | 曲名 | 用途 |
|---|---|---|
| title.mp3 | Heartbreaking | 标题主旋律 |
| calm.mp3 | Meditation Impromptu 01 | 日常 / 公路 |
| tense.mp3 | Lightless Dawn | 裁员 / 断药等压抑情节 |
| sad.mp3 | Sovereign | 水仙花山坡 / 海滩高潮 |
| end.mp3 | Meditation Impromptu 02 | 尾声 |

## 插画

8 张场景插画为 AI 生成的原创作品，学习对象为《水仙 Narcissu》的视觉风格
（柔光水彩 + 纤细素描线条 + 高调过曝 + 大面积留白），未直接使用任何第三方图片。

## Engine script format

```js
{ bg:'beach' }              // 切换背景（淡入淡出）
{ music:'sad' }             // 切换 BGM
{ chapter:'第一章：七楼' }   // 章节卡
{ n:'...' }                 // 旁白
{ say:['Serena','...'] }    // 对白
{ choice:[{t, do?, goto?}] }// 分支选项（do = 内联剧情，goto = 跳转）
{ jump:'ch2' }              // 跳转
{ end:true }                // 终幕
```

## Deploy (GitHub Pages)

Settings → Pages → Source: Deploy from a branch → Branch: main, /(root).
每次 push 自动重新部署。
