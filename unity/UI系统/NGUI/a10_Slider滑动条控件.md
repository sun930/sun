## 制作
 1. 3个sprite 1个做根对象为背景 2个子对象 1个进度 1个滑动块
 2. 设置层级
 3. 为根背景添加slider脚本
 4. 添加碰撞器(父对象或者滑块)
 5. 关联3个对象

## 参数

![[assets/Pasted image 20261014201000.png]]
- Value 当前值0~1
- Steps 步数 将1平分
- Appearance 外观设置
  - Foreground 前景（用于缩放）
  - Background 背景
  - Thumb 拖动块
  - Direction 拖动方向
    ![[assets/Pasted image 20261014201159.png|341]]
    从左到右、从右到左、从下到上、从上到下
- OnValueChange  值变化时监听脚本