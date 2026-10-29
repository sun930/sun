## 制作
1. 2个sprite 1父1子
2. 为父对象添加Toggle脚本
3. 添加碰撞器

## 参数
![[assets/Pasted image 20261013163310.png]]
- Group 
  多选框分组
  多个多选框分为一组则变为单选框
	  - State of None 单选框状态时 是否允许不选中
- Starting State
  开始默认状态勾选为选中
- Sprite 选中用图片
- Invert State反装状态
  如果选中不显示。不选中显示  就勾选它
- Animator  状态变化时播放动画(新动画系统)
  Animation  状态变化时播放动画(老动画系统)
  Tween  状态变化时缓动
- Transition  过渡模式
- OnValueChange  状态变化时响应脚本
  