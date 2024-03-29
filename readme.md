[TOC]

# Bot 对战平台

## 1.给玩家

在 [游戏 Snake-Botzone](https://www.botzone.org.cn/game/Snake)，有许多刺激的对局。Bot Battle 项目是对该比赛平台的拙劣模仿。


- 在 我的 Bots 页面查看并管理自己的 Bot
- 游戏开始前，决定使用玩家上传的寻路代码（或玩家手动使用键盘 W/S/A/D 操作）控制你的蛇
- 两条蛇初始位于地图对角，地图最外围一圈为障碍物，地图内部每局随机生成障碍物
- 代码执行（或者键盘输入），蛇移动
- 每回合超过 5 秒不输入判定为出局
- 玩家若下一回合移动的目标位置为障碍物或某条蛇的身体部位则死亡
- 需要注册并登录后才能访问各个页面
- 每名玩家初始天梯分为 1500，赢得比赛获得天梯分

> 注意，暂时只支持`.java`代码

向您强烈推荐以下最简单的寻路算法示例，您可以把它作为创建的第一个 Bot。如果用更强的算法，请参考该 Bot 的 I/O：

```
package com.kob.botrunningsystem.utils;

import java.io.File;
import java.io.FileNotFoundException;
import java.util.ArrayList;
import java.util.List;
import java.util.Scanner;

public class Bot implements java.util.function.Supplier<Integer>{
    static class Cell{
        public int x,y;
        public Cell (int x, int y){
            this.x = x;
            this.y = y;

        }
    }

    private boolean check_tail_increasing(int step){ //检验当前回合，蛇的长度是否增加
        if(step<=10) return true;
        return step % 3 == 1;
    }

    public List<Cell> getCells(int sx, int sy, String steps){
        steps = steps.substring(1, steps.length()-1);
        List<Cell> res=new ArrayList<>();
        int[] dx={-1,0,1,0}, dy={0,1,0,-1};

        int x =sx, y=sy;
        int step=0;
        res.add(new Cell(x, y));
        for(int i=0; i<steps.length();i++) {
            int d = steps.charAt(i) - '0';
            x+=dx[d];
            y+=dy[d];
            res.add(new Cell(x,y));
            if(!check_tail_increasing(++step)){
                res.remove(0);
            }
        }
        return res;
    }

    public Integer nextMove(String input) {
        String[] strs = input.split("#");
        int[][] g = new int[13][14];
        for (int i = 0,k=0; i <13 ; i++) {
            for (int j=0; j< 14;j++,k++){
                if (strs[0].charAt(k)=='1'){
                    g[i][j]=1;
                }
            }
        }
        int aSx = Integer.parseInt(strs[1]), aSy = Integer.parseInt(strs[2]);
        int bSx = Integer.parseInt(strs[4]), bSy = Integer.parseInt(strs[5]);


        List<Cell> aCells = getCells(aSx, aSy, strs[3]);
        List<Cell> bCells = getCells(bSx, bSy, strs[6]);

        for (Cell c:aCells) g[c.x][c.y]=1;
        for (Cell c:bCells) g[c.x][c.y]=1;
        int[] dx={-1,0,1,0}, dy={0,1,0,-1};
        for(int i=0;i<4;i++){
            int x=aCells.get(aCells.size()-1).x +dx[i];
            int y=aCells.get(aCells.size()-1).y +dy[i];
            if(x>=0 && x<13 && y>=0 && y<14 && g[x][y]==0){
                return i;
            }
        }

        return 0;

    }

    @Override
    public Integer get() {
        File file = new File("input.txt");
        try {
            Scanner sc = new Scanner(file);
            return nextMove(sc.next());
        } catch (FileNotFoundException e) {
            throw new RuntimeException(e);
        }

    }
}
```

## 2.给开发者

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
