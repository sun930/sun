## 参数
### Panel（可视区域）
![[assets/Pasted image 20261015170859.png|339]]
## Scroll View
![[assets/Pasted image 20261015170641.png|342]]
- <font color="#ff0000"> Content Origin  内容子对象对其方式</font>
- <font color="#ff0000"> Movement 拖曳的方向</font>
  ![[assets/Pasted image 20261016154920.png]]
  水平、垂直、自由、自定义
- <font color="#ff0000">Drag Effect  拖动特效</font>
  ![[assets/Pasted image 20261016161801.png]]
  不使用任何效果
  动量(惯性)效果(差异不明显)
  动量(惯性)和弹力效果
- <font color="#ff0000">Scroll Wheel Factor</font>
  滚动因子
  如果不为0，鼠标中间滚动可以滚动它
  可以通过它控制速度和方向
- <font color="#ff0000">Momentum Amount</font>
  动量
  拖曳一下鼠标，动的快慢
  可以理解成惯性大小
- <font color="#ff0000">Sppring Strength</font>
  弹力大小
  移动到边缘时弹回时弹力大小
- Dampen Strength
  阻尼强度影响回弹效果
- Restrict Within Panel
  限制在Panel中
  不勾选，不会产生弹力效果
- Constrain On Drag  阻力约束，一般不修改
- <font color="#ff0000">Cancel Drag if fits</font>
  若勾选
  滚动视图的内容是否应该是可拖动的
  取决于它们当前子对象大小是否溢出
- Smooth Drag Start  平滑拖动，一般不修改
- IOS Drag EmulationIOS  
- 阻力模拟，一般不修改
## Scrollbar Bars
![[assets/Pasted image 20261016163419.png|435]]
- Horizontal  水平滚动条
- 竖直滚动条
- ShowCondition  显示时机
  ![[assets/Pasted image 20261016163458.png]]
  一直显示、需要时显示、拖动时显示
