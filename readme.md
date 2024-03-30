[TOC]

## 1.游玩

### 1.1 欢迎阅读

> <a href="https://www.cnblogs.com/aijisjtu/p/18105385" target="_blank">BotBattle-玩家手册</a>

↑ 详细介绍，请见该博客~↑

### 1.2 快速开始

游戏网址：<a href="https://app6735.acapp.acwing.com.cn/" target="_blank">app6735.acapp.acwing.com.cn</a>

![](https://img2024.cnblogs.com/blog/3387348/202403/3387348-20240330125702599-1233512050.png)

欢迎您在<a href="https://www.cnblogs.com/aijisjtu/p/18105385" target="_blank">博客</a>评论或<a href="https://github.com/aijisjtu/Bot-Battle/issues/" target="_blank">Issues</a>反馈~ BotBattle 非常需要您的留言建议！

## 2.开发

在线程序对抗平台 <a href="https://www.botzone.org.cn/" target="_blank">www.botzone.org.cn</a>承办过许多 AI 对抗比赛，其中的 Bot 上演了无数精彩刺激的游戏对局

本项目 Bot Battle 是对这款 <a href="https://www.botzone.org.cn/game/Snake/" target="_blank">Snake-Botzone 游戏</a> 的拙劣模仿

### 2.1 模块

- PK
  - 匹配界面（微服务）
  - 实时直播（WebSocket）
  - 玩家 PK（WebSocket）
  - Bot 代码执行（微服务）
- 对战列表
  - 录像回放
- 排行榜
  - 对局排名
- 用户中心
  - 注册
  - 登录
  - 我的 Bot

### 2.2 图解

<img src="https://ice2604-navi.github.io/asssets/botbattle.jpg" alt="图片alt" title="图片title">

<center><font color=gray>图片来源：<a href="https://gitee.com/XZHongAN" target="_blank" alt="图片alt" title="图片title">gitee.com/XZHongAN</a> </font></center>

### 2.3 细节亮点

- 地图内部每局随机生成障碍物满足中心对称，两名玩家必定连通，由于地图大小为 13×14，长和宽中有一个奇数有一个偶数，所以蛇头不会在同一回合走到同一个格子上
- 匹配时优先匹配分值接近的玩家，若匹配时间较长则会匹配分值差距较大的玩家
