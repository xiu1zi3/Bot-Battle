
## 1.游玩

### 1.1 欢迎阅读

> <a href="https://www.cnblogs.com/aijisjtu/p/18105385" target="_blank">BotBattle-玩家手册</a>

↑ 详细介绍，请见该博客~↑

### 1.2 快速开始

<!-- ![](https://img2024.cnblogs.com/blog/3387348/202403/3387348-20240330125702599-1233512050.png) -->

1. 进入 <a href="https://app6735.acapp.acwing.com.cn/" target="_blank">游戏网址</a>

2. 登录体验账号

   > 用户名
   > `Alice`
   > 密码
   > `123456`

   > 用户名
   > `Bob`
   > 密码
   > `123456`

3. 您在登录账号后，请打开**另一款浏览器**，登录**另一个账号**

   > 这是因为，在线玩家不够，恐怕需要您安排 2 个号组成对局（除非您和伙伴同时上线）

4. 选择喜欢的 Bot，并开始匹配

5. 对局结束后，可在**对局列表**观看比赛回放，在**排行榜**查看天梯积分

- “常规游玩”介绍请见 <a href="https://www.cnblogs.com/aijisjtu/p/18105385" target="_blank">BotBattle-玩家手册</a>

<!--
### 1.3 常规游玩

1. 前往复制 [最基础代码](https://www.cnblogs.com/aijisjtu/p/18105385#3%E6%8E%A8%E8%8D%90%E7%9A%84%E7%A4%BA%E4%BE%8B%E4%BB%A3%E7%A0%81) 到剪切板

   > 这有助于您开始游戏，且对于您熟悉 Bot 代码的 I/O 进而创建其他 bot 很有意义

2. 进入游戏网址 <a href="https://app6735.acapp.acwing.com.cn/" target="_blank">app6735.acapp.acwing.com.cn</a> 将提供的代码创建为您的第一个 bot

3. 打开另一款浏览器。接下来与 **1.2 快速开始** 步骤相同 -->

## 2.开发

语言、框架：
<div align="center">
<img src="https://img.shields.io/badge/-Java-important?style=for-the-badge" />
<img src="https://img.shields.io/badge/-Spring%20Boot-brightgreen?style=for-the-badge" />
<img src="https://img.shields.io/badge/-Spring%20Cloud-blue?style=for-the-badge" />
</div>
组件、中间件等：
<div align="center">
<img src="https://img.shields.io/badge/-MySQL-yellow" />
<img src="https://img.shields.io/badge/-WebSocket-1af442"/>
<img src="https://img.shields.io/badge/-Docker-83ef12" />
<img src="https://img.shields.io/badge/-Nginx-pink"/>
</div>

### 2.1 图解

<img src="https://ice2604-navi.github.io/asssets/botbattle.jpg" alt="图片alt" title="图片title">

<center><font color=gray>图片来源：<a href="https://gitee.com/XZHongAN" target="_blank" alt="图片alt" title="图片title">gitee.com/XZHongAN</a> </font></center>

### 2.2 模块

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

### 2.3 细节

- 障碍物生成
  内部障碍物每局随机生成，地图满足中心对称，两名玩家必定连通
- 双方蛇头不会相遇
  可以这样想：地图大小为 13×14，长和宽中有一个奇数有一个偶数。双方不可能在同一回合走到同一个格子上
- 等待时间与匹配顺序
  匹配时优先匹配分值接近的玩家，若匹配时间较长，即使分值差距较大也会优先匹配

---

在线程序对抗平台 <a href="https://www.botzone.org.cn/" target="_blank">www.botzone.org.cn</a>承办过许多 AI 对抗比赛，其中的 Bot 上演了无数精彩刺激的游戏对局

本项目 Bot Battle 是对这款 <a href="https://www.botzone.org.cn/game/Snake/" target="_blank">Snake-Botzone 游戏</a> 的拙劣模仿

欢迎您在<a href="https://www.cnblogs.com/aijisjtu/p/18105385" target="_blank">博客</a>评论或<a href="https://github.com/aijisjtu/Bot-Battle/issues/" target="_blank">Issues</a>反馈~ BotBattle 非常需要您的留言建议！
