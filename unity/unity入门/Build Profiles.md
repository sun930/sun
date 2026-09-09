![[assets/Pasted image 20260909093257.png]]

- <font color="#c0504d">Scene List（场景列表快捷入口）</font>
  快速查看项目参与打包的场景。
- <font color="#c0504d">**Platforms（平台列表）**</font>
  - **Active**：绿色标签，代表当前激活、正在配置的打包平台（图中是 Windows）。
  - 点击任意平台，切换到对应平台的打包配置。
- <font color="#c0504d">Build Profiles（打包配置集）</font>
  核心新功能：可以保存多套独立打包配置，每套配置拥有独立场景列表、平台参数。
  - `Add Build Profile`：新建一套打包配置文件，可以团队共享。
  - 作用：比如一套 PC 发布包、一套 PC 测试包，一套安卓包，不用反复改参数来回切换。
## 二、右侧主配置区（当前：Windows 平台）

### 顶部提示框

1. **Diagnostics Data**：Unity 诊断数据，新项目默认开启，收集编辑器运行数据，`Dismiss`可以关闭提示。
2. **Platform builds use the shared scene list**

> 默认情况下，不同平台共用一套场景列表。如果希望不同平台打包不同场景，点击`Add Build Profile`创建独立配置集。
### Scene List 场景列表

```
☑ Scenes/BeginScene  序号0
☑ Scenes/GameScene   序号1
```

- 打勾：该场景会被打进游戏包；取消勾选打包会忽略该场景。
- 数字：场景加载序号，<font color="#ff0000">**0 号为游戏启动第一个场景**。</font>
- `Open Scene List`：打开窗口管理所有打包场景。
- 

### Platform Settings (Windows) 平台参数

| 参数                            | 说明                                                                   |
| ----------------------------- | -------------------------------------------------------------------- |
| Architecture                  | 架构，Intel 64‑bit：64 位 PC 程序                                           |
| Build and Run on              | Build And Run 运行目标，Local Machine = 本机                                |
| Copy PDB files                | 复制调试符号文件，调试版本开启，正式发布关闭。<br>开启后可以在打包出的数据中<br>包含程序数据库文件，之后可以用于调试应用程序   |
| Create Visual Studio Solution | 生成 VS 解决方案源码工程，仅源码调试用<br>可以在VS中进行正式的打包可以设置更多额外信息                     |
| Development Build             | **开发构建**：测试包，开启日志、调试；正式打包务必取消勾选<br>启用后，会在打包出的版本中开启性能分析器，之后可以用于调试     |
| Autoconnect Profiler          | 启用Development Build后才有用<br>开启后Unity性能分析器可以自动连接到你的打包项目                |
| Deep Profiling Support        | 启用Development Build后才有用<br>开启后，性能分析器可以分析到每个函数的调用来获取更详细数据             |
| Script Debugging              | 启用Development Build后才有用开启后，Unity会将调试符号添加到脚本代码中                       |
| Compression Method            | 资源压缩方式，Default 默认<br>LZ4快速压缩格式<br>LZ4HCLZ4的高度压缩变体<br>构建速度会变慢，但是压缩效果好 |
### Diagnostics

Diagnostics Data：诊断数据开关，项目默认配置。



### 底部按钮

1. **Build**：仅打包，弹出文件夹选择，输出游戏程序。
2. **Build And Run**：打包完成后，直接运行生成出来的游戏。

### Player Settings
![[assets/Pasted image 20260909143511.png]]

- Company Name 公司名
- Product Name 项目名（游戏名）
- Version 版本号
- Default Icon 默认图标
- Default Cursor 默认鼠标光标图
- Cursor Hotspot 鼠标图偏移位置
- Icon 自定义各尺寸的游戏图标
- Resolution and Presentation设置窗口、分辨率相关
  - Resolution
    - Fullscreen Mode全屏模式:
	    1. FullscreenWindow保持显示器分辨率全屏如果分辨率不足会有黑边
	    2. Exclusive Fullscreen会改变显示器分辨率来适配自己的项目也是全屏模式
	    3. Maximized Window最大化窗口模式
	    4. Windowed窗口模式
	- Default Is Native Resolution勾选时，使用显示器分辨率取消勾选是，使用设置的分辨率(窗口模式才有用)
	- Default Screen Height游戏画面默认高度，窗口模式才有用
	- Run In background开启后，程序失去焦点时可以继续运行而不是暂停
	
	    
	 
		
