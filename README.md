# ReinforcementCar
A DL course project

# Task
- Game
赛车游戏，车辆逐渐加速，方向键左右控制方向，转向的角速度随按下方向键的时间增大，转向时逐渐减速，

- RL model

- Visualization
模型可视化，展示运行过程中的模型推理

# 接口定义
- render()：
  当前游戏画面渲染
- step(action, training=True)：
  游戏向前运行一帧
  
  **在这里同时也要读取玩家的键盘输入**
  
  params:
  
    - action:发出的动作指令，0为不转向，1为左转，2为右转
    - training:是否在训练，为False则还需要读取玩家键盘输入
    - reward:用于显示在屏幕上的reward数值，由训练脚本提供
  
  return：
    
    - observation: 目前车辆五个方向距障碍物的距离数组[l1,l2,l3,l4,l5]
    - terminal: 游戏是否结束，0为未结束，1为失败，2为成功（游戏结束后不会再调用step方法）
    
- reset()：
  重置游戏状态
    
- destroy():
  退出游戏
