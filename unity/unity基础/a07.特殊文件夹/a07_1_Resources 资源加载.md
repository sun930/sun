
## 核心概念
`Resources`：Unity 特殊文件夹，**打包会把所有 Resources 下资源打进包**。 
作用：**代码动态加载资源，不用 Inspector 拖拽赋值**。
>规则：项目里可以有多个同名`Resources`文件夹，API 自动搜索全部。

## 加载资源类型

1. **GameObject 预制体**：加载得到配置数据 → **必须 Instantiate 实例化才会出现在场景**
2. **AudioClip 音效**：加载完直接赋值 AudioSource.clip，不需要实例化
3. **TextAsset 文本**：txt/json/xml/csv/html/bytes，`.text`读文本，`.bytes`读字节
4. **Texture 图片**：加载纹理，可用于 GUI、材质
5. 其他资源：需要什么就指定什么类型

## 同步加载 API（重点）
- <font color="#00b0f0">普通重载</font>
```csharp
  //基础
  Resources.Load("路径"); 
  //指定类型，解决同名资源冲突 
  Resources.Load("路径", typeof(类型)); 
  //加载文件夹下全部同名资源 
  Resources.LoadAll("路径");
```
  
- <font color="#00b0f0">泛型重载</font>
  ```csharp
  Resources.Load<类型>("路径");
  ```
> ⚠️坑点

1. 预制体：Load 只是把资源读到内存，**不生成场景物体，一定要 Instantiate**
2. 音效 / 文本 / 图片：加载完直接使用，**不要实例化**
3. 同路径同名不同格式资源：直接 Load 会拿错，必须指定类型`typeof()`
4. 路径写法：`"文件夹/资源名"`，**不带后缀名**
```csharp
//预制体 
Object prefab = Resources.Load("Cube"); 
Instantiate(prefab); 

//音效 
audioS.clip = Resources.Load<AudioClip>("Music/LSM"); 
audioS.Play(); 

//文本 
TextAsset ta = Resources.Load<TextAsset>("Txt/Test"); 
print(ta.text); 

//图片 
Texture tex = Resources.Load<Texture>("Tex/Monesy");
```