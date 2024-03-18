[TOC]

## Bot对战平台

### 图解

<img src="https://ice2604-navi.github.io/asssets/botbattle.jpg" alt="图片alt" title="图片title">

<center><font color=gray>图片来源：<a href="https://gitee.com/XZHongAN/king-of-bots" alt="图片alt" title="图片title">XZHongAN</a> </font></center>


### 
- 玩家（两条蛇）初始位于地图对角，地图大小为 13×14，最外围一圈为障碍物，地图内部每局随机生成障碍物，满足中心对称。
- 随机地图保证玩家出生地不为障碍物，两名玩家必定连通，且不会在同一回合走到同一个格子上。
- 玩家若下一回合移动的目标位置为障碍物或某条蛇的身体部位则死亡。
- 目前实现两名玩家的匹配联机对战，使用键盘 `W/S/A/D` 操作移动，每回合超过 5 秒不输入判定为自杀。
- 需要注册并登录后才能访问各个页面。
- 用户可以在 My Bots 页面查看并管理自己的 Bot（包括名称、创建时间、简介、代码等信息），创建、修改或删除 Bot。
- 每名玩家初始天梯分为 1500，匹配时优先匹配分值接近的玩家，若匹配时间较长则会匹配分值差距较大的玩家。


### 实现模块

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
