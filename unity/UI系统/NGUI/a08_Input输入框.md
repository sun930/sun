## 参数
![[assets/Pasted image 20261014110429.png|433]]
- <font color="#ff0000">Label  关联的文本组件</font>
- Starting Value  开始默认显示的内容
- Saved As
  若此处填写内容:
  会使用PlayerPrefs将输入内容作为此处填写的该key的值进行存储
  一般不使用
- <font color="#ff0000">ActiveTextColor  选中激活时颜色</font>
- <font color="#ff0000"> Inactive Color  未选中失活时颜色</font>
- <font color="#ff0000">Caret Color  插入光标的颜色</font>
- <font color="#ff0000">Selection Color  选中文字的背景颜色</font>
- <font color="#ff0000">InputType  输入类型</font>
  ![[assets/Pasted image 20261014110815.png|340]]
  默认模式、自动更正、密码输入(输入内容看不到)
- <font color="#ff0000">Validation 输入限制</font>  ![[assets/Pasted image 20261014111255.png]]
  None：无限制
  Integer：只能输入整形
  Float：可以输入浮点型
  Alphanumeric：只能是数字和字母
  Username：用户名
  Name：姓名
  Filename：文件名
- Mobile Keyboard  手机键盘模式
  ![[assets/Pasted image 20261014111801.png]]
  英文、数字符号、连接、数字、手机、名字、邮箱地址
- Hide Input  键盘下 隐藏输入框
- <font color="#ff0000">On Return Key  完成键(回车键)  做什么操作</font>
  ![[assets/Pasted image 20261014111921.png]]
- <font color="#ff0000">Character Limit  最大可输入字符数</font>
- <font color="#ff0000">OnSubmit  输入完成时响应脚本</font>
- <font color="#ff0000">OnChange  输入变化时响应脚本</font>