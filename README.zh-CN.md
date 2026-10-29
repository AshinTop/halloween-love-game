[English](README.md) · [简体中文](README.zh-CN.md) · [Español](README.es.md) · [Português (Brasil)](README.pt-BR.md) · [日本語](README.ja.md)

# Haunted Hearts 双幽灵心动逃脱 — 万圣节双角色合作解谜

👻 两只小幽灵、两半爱心，还有一盏要轮流拿的灯。和露娜、罗丝一起穿过八个温柔的鬼屋房间：有时走向出口之前，要先为伙伴留一扇门。你可以独自切换角色解谜，也可以和身边的人共用一台设备，商量着轮流行动。

**[立即试玩](https://halloween-love-game.crazy3d.org/)** · [浏览全部 12 款万圣节游戏](https://github.com/AshinTop/halloween-games) · [⭐ 在 GitHub 点亮 Star](https://github.com/AshinTop/halloween-love-game)

README 提供五种语言版本。**游戏界面目前仅支持英语和简体中文**；文档翻译不代表新增了对应界面语言。

![双幽灵心动逃脱的万圣节房间，包含露娜、罗丝、双色爱心、机关门和共享灯笼](docs/images/gameplay.jpg)

## 这款游戏有什么特别

- 八个单屏房间，逐步加入机关门、专属地砖和传灯合作。
- 两名角色独立行动，各自收集半颗爱心并回到自己的拱门。
- 无限撤销、重新开始，以及根据当前位置计算下一步的真实提示。
- 记录每关最佳步数，通过房间链接邀请朋友尝试相同谜题。
- 原创 SVG 幽灵与场景、可关闭的合成音效、触屏与键盘操作，并支持减少动态效果。

## 怎么玩

先选择露娜或罗丝，再移动当前角色。露娜收集蓝色半心、使用蓝色月亮地砖，最后回到蓝色拱门；罗丝对应粉色半心、玫瑰地砖和粉色拱门。两颗心都拿到、两名角色都站在各自终点，房间才算完成。两只幽灵不能占同一格。

月亮和星星踏板只有在**有人站着时**才会让对应的门保持打开。离开踏板之前，看看伙伴是否还要经过那扇门。有些房间可以让另一名角色接替另一侧踏板，给先前的守门者放行。

只有携带灯笼的角色能**进入迷雾**。两人相邻时可以传灯；已经站在雾里的角色即使交出了灯，也能走出迷雾。这条规则是后半段合作过路的重要线索。

八关从简单相会逐步发展到同时安排开门、让路与传灯。没有倒计时，也不限制总步数。各关从起点出发的已验证最短路线依次为 **8、18、22、20、19、24、28、30 步**，适合通关后挑战，不是过关门槛。

## 操作方式

| 操作 | 输入方式 |
| --- | --- |
| 选择角色 | 点击头像或棋盘上的幽灵；**Q** 切换 |
| 移动 | 方向键 / **WASD**、屏幕方向按钮，或点击相邻格 |
| 传递灯笼 | 两人相邻时按 **L** 或点击传灯按钮 |
| 撤销一步 | **Z** 或撤销按钮 |
| 提示、重开、选关 | 使用对应的游戏内按钮 |

## 一点小策略

先安排好帮忙的角色站在哪里，再让伙伴穿门。狭窄通道里要留出相邻格，才能顺利交接灯笼。提示会从**当前局面**计算最短路线，选中需要行动的角色并告诉你下一步，但不会自动代走。如果当前状态已经无解，可以撤回几步重新安排。

## 存档与挑战链接

已完成房间的最佳步数、语言和音效偏好保存在当前浏览器。刷新后会重新开始当前房间，不恢复尚未通关时逐步移动的过程。不同设备之间不自动同步。

例如[第六个房间](https://halloween-love-game.crazy3d.org/#room=6)的链接会从该关起点开始。分享功能复制真实通关步数和房间链接，不上传回放；剪贴板不可用时，会显示文字供手动复制。

## 实机界面截图与视频介绍

![双幽灵心动逃脱的紧凑播放器，保留两名角色选择和屏幕方向按钮](docs/images/mobile.jpg)

实际游戏在紧凑浏览器 iframe 中的截图，用于展示小窗口布局，不代表实体手机测试。

[打开视频播放器与文字介绍](https://halloween-love-game.crazy3d.org/intro.html) · [下载 MP4](docs/media/intro.mp4)

**24 秒无声介绍视频**由真实游戏截图与字幕编排而成，用于介绍画面与玩法，并非连续操作录像或音效演示。

## 常见问题

### 一定要两个人玩吗？

不需要。一个人切换两个角色就能完成全部房间。两个人也可以共用设备讨论和轮流操作；当前没有跨设备联机。

### 门为什么关了，或迷雾为什么进不去？

门需要对应踏板持续被占用；进入雾格需要手持灯笼。移动负责帮忙的角色前，先检查这两个条件。

### 这是测爱情匹配度的游戏吗？

这是爱心与幽灵主题的合作逻辑游戏，不要求输入姓名，也不评价关系或计算匹配分数。

## 本地运行与嵌入

在仓库根目录启动 HTTP 服务：

```sh
python3 -m http.server 4173
```

打开 **http://localhost:4173/**。无需构建或安装依赖；直接使用 `file://` 可能阻止 JavaScript 模块加载。

使用 Node 运行内置检查：

```sh
npm test
```

内置检查覆盖八关完整解法、墙壁与角色碰撞、专属地砖、踏板开门、传灯、进入迷雾及无效房间链接。

```html
<iframe src="https://halloween-love-game.crazy3d.org/?embed=1"
  title="Haunted Hearts"
  style="display:block;width:100%;height:521px;border:0"
  allow="fullscreen" allowfullscreen></iframe>
```

主站桌面窗口约 **833×521**。浏览器检查也覆盖 **356×280、326×280、390×650、844×340**。特别矮的窗口请使用始终保留的方向按钮；条件允许时，手机游戏区域建议有 **480 px 或更高**。嵌入 iframe 会自动启用紧凑布局，`?embed=0` 可切回完整页面。

尺寸、存储、焦点和权限说明见[嵌入文档](EMBEDDING.md)。请按扣除主站工具栏后的实际剩余高度设置 iframe。

## 继续逛逛万圣节小游戏集

- **[Moonlit Mirrors](https://halloween-mirror-hearts.crazy3d.org/)** · [源码](https://github.com/AshinTop/halloween-mirror-hearts) — 用镜像移动同时引导两只幽灵回家。
- **[Ghost Lanterns 3D](https://halloween-3d.crazy3d.org/)** · [源码](https://github.com/AshinTop/halloween-3d) — 用翻灯规则与灵魂连线点亮南瓜花园。
- **[Witch’s Candy Blocks](https://halloween-block-blast.crazy3d.org/)** · [源码](https://github.com/AshinTop/halloween-block-blast) — 在 8×8 棋盘摆放糖果方块，完成魔药订单。
- **[Pumpkin Jam](https://halloween-sprunki.crazy3d.org/)** · [源码](https://github.com/AshinTop/halloween-sprunki) — 组建四声部小怪物乐队，再挑战幽灵回声。

## 创作说明与支持

为 **AshinTop** 与 **Midnight Candy Club** 制作，由人主导、AI 辅助设计、编程和审查。插画与合成音效为本项目创作。游戏无需远程账号；托管服务可以独立加入脚本或请求日志。

喜欢的话，欢迎**[点亮 GitHub Star](https://github.com/AshinTop/halloween-love-game)**。反馈问题时，请附浏览器、iframe 尺寸、挑战链接与复现步骤。
