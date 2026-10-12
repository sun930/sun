## 参数
![[assets/Pasted image 20261012151007.png|450]]
- Font
  使用Unity字体可以使用fft的字体文件
  也可以使用NGUI字体图集
- Material 材质 一般不会修改
- FontSize 字体大小
  ![[assets/Pasted image 20261012151339.png|430]]
  普通、加粗、斜体、加粗并斜体
- Text 显示内容
- Modifier 修饰方式 强制大小写字母
  ![[assets/Pasted image 20261012152002.png]]
  没有限制、大写字母、小写字母、自定义
- Overflow
  ![[assets/Pasted image 20261012152317.png|459]]
  - Shrink Content
    收缩内容
	文字显示的大小与Label的大小自动适应:
	Labe控件尺寸不足显示较大字体时
	字体的尺寸会自动适应Label控件的尺寸
  - Clamp Content
    夹紧内容
	裁减掉无法显示的字体内容
	字体会按照FontSize大小来显示
	如果Label控件大小不足以装下字体时:
	对应内容被裁剪掉不会显示
  - Resize Freely
    自动调整大小
	Label大小去适应字体内容的大小
  - Resize Height
    自动调整高
	Label控件高度无法手动调节
	会随着字体内容的大小需求去适配字体内容
	只能手动调节Label控件的宽度
- Alignment 对其方法
  