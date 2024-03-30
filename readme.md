[TOC]

## 1.游玩

### 1.1 欢迎阅读

> [BotBattle-玩家手册](https://www.cnblogs.com/aijisjtu/p/18105385)

↑ 详细介绍，请见该博客~↑

### 1.2 快速开始

游戏网址：[app6735.acapp.acwing.com.cn](app6735.acapp.acwing.com.cn)

![](https://img2024.cnblogs.com/blog/3387348/202403/3387348-20240330125702599-1233512050.png)

欢迎您在[博客](https://www.cnblogs.com/aijisjtu/p/18105385)下方或[Issues](https://github.com/aijisjtu/Bot-Battle/issues)反馈~ BotBattle 非常需要您的留言建议！

## 2.开发

在线 AI 对抗网站 [www.botzone.org.cn](https://www.botzone.org.cn/)里，有无数精彩刺激的对局
我的 Bot Battle 项目是对其中的这款[游戏 Snake-Botzone](https://www.botzone.org.cn/game/Snake)的拙劣模仿

### 2.1 模块

- PK
  - 匹配界面（微服务）
  - 实时直播（websocket）
  - 玩家 PK（websocket）
  - Bot 代码执行（微服务）
- 对战列表
  - 录像回放
- 排行榜
- 用户中心
  - 注册
  - 登录
  - 我的 Bot
  - Bot 的记录

### 2.2 图解

<img src="https://ice2604-navi.github.io/asssets/botbattle.jpg" alt="图片alt" title="图片title">

<center><font color=gray>图片来源：<a href="https://gitee.com/XZHongAN/king-of-bots" alt="图片alt" title="图片title">XZHongAN</a> </font></center>

### 2.3 细节亮点

- 地图内部每局随机生成障碍物满足中心对称，两名玩家必定连通，由于地图大小为 13×14，长和宽中有一个奇数有一个偶数，所以蛇头不会在同一回合走到同一个格子上
- 匹配时优先匹配分值接近的玩家，若匹配时间较长则会匹配分值差距较大的玩家
