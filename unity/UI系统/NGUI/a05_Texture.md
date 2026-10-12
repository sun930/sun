Texture是用于显示不用打进图集的大图片的

## 参数
![[assets/Pasted image 20261012170451.png|397]]
- Texture 图片资源
- Material 材质一般不改
- Shader 着色器 一般不改
- Type 图片类型
  ![[assets/Pasted image 20261012170655.png]]
  - Simple 普通模式，缩放会拉伸
  - Sliced 切片模式，可九宫格缩放
  - Tiled 平铺模式 图片重复绘制
  - Filed 填充模式 可以做CD，进度条等
  - Advanced 高级模式 可以把图片分成5个部分分别设置模式
- Flip 翻转模式
  ![[assets/Pasted image 20261012170811.png]]
  水平、竖直、水平竖直
- Gradient 渐变色
  上部颜色和下部颜色自动渐变
- Color Tint
  颜色叠加