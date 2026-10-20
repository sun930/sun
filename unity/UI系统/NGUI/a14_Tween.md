## Tween 参数
![[assets/Pasted image 20261021015454.png|428]]

- <font color="#ff0000">From 开始状态</font>
- <font color="#ff0000">To 结束状态</font>
- <font color="#ff0000"> PlayStyle 播放方式</font>
  ![[assets/Pasted image 20261021014028.png]]
  一次、循环、循环 从头到尾 从尾到头
- Animation Curve 动画曲线 
  可以调整两个值的变化曲线
- <font color="#ff0000">Duration  持续时间</font>
- <font color="#ff0000">Start Delay  开始播放前的延迟时间</font>
- Delay Affects  延迟影响
- <font color="#ff0000">TweenGroup</font>
  分组ID
  用于一个对象多个动画时分组
- <font color="#ff0000">lgnore TimeScale  忽略时间暂停</font>
- Use Fixed Update  使用物理更新更新动画

## Play Tween
![[assets/Pasted image 20261021015757.png|426]]
- <font color="#ff0000">Tween Target  控制对象</font>
- <font color="#ff0000">Include Children  是否带着子对象一起变化</font>
- <font color="#ff0000">Start State</font>
  如果为真，则在激活触发之前
  Play Tween将在启动时将所有关联的Tween重置为其起始状态
- <font color="#ff0000">TweenGroup  控制的是哪一组缓动</font>
- <font color="#ff0000">Trigger condition  触发条件</font>
  ![[assets/Pasted image 20261021015923.png]]
- <font color="#ff0000">Play direction</font>
  ![[assets/Pasted image 20261021015952.png]]
  Reverse关闭功能
  Togale开关状态转换