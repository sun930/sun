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

⚙ Platform Settings (Windows) 平台参数

|参数|说明|
|---|---|
|Architecture|架构，Intel 64‑bit：64 位 PC 程序|
|Build and Run on|Build And Run 运行目标，Local Machine = 本机|
|Copy PDB files|复制调试符号文件，调试版本开启，正式发布关闭|
|Create Visual Studio Solution|生成 VS 解决方案源码工程，仅源码调试用|
|Development Build|**开发构建**：测试包，开启日志、调试；正式打包务必取消勾选|
|Autoconnect Profiler|打包后自动连接性能分析器，调试用|
|Deep Profiling Support|深度性能剖析，性能调试，会大幅降低运行速度|
|Script Debugging|脚本调试，允许 VS 附加调试游戏程序|
|Compression Method|资源压缩方式，Default 默认|
### Diagnostics

Diagnostics Data：诊断数据开关，项目默认配置。

### 右上角标签

1. **Player Settings**：跳转到项目玩家设置（版本号、公司名、图标、分辨率、权限等）
2. **Asset Import Overrides**：资源导入覆盖，针对该套打包配置修改资源导入参数。

### 底部按钮

1. **Build**：仅打包，弹出文件夹选择，输出游戏程序。
2. **Build And Run**：打包完成后，直接运行生成出来的游戏。