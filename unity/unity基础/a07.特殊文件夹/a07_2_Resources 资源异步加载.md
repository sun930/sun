<font color="#ffc000">同步加载Why卡顿</font>
![[assets/Pasted image 20260917152927.png|625]]
游戏应用程序本质一个死循环,每一次循环就是一帧，假如60帧(一秒跑60次)，一次循环【跑下来16.6ms，同步加载在执行这一帧的时候，假设途中进行同步加载（把硬盘上的一个数据，加载到内存上存储）这个过程可能会卡顿。假设这个资源非常大，同步加载一定会把所有内容加载到内存过后才会继续执行这一帧后面的内容。由于这个资源很大，计算量非常多，它的时间可能就会>16.6ms，意味着一秒钟就跑不到60帧，可能就会形成掉帧

![[assets/Pasted image 20260917155138.png|509]]
主线程异步加载资源，在执行异步加载时会新开一个线程，把你要加载的资源告诉这个新开的线程，这个线程有自己一套逻辑，专门去加载这个资源。新线程加载的时候，主线程不用管了。继续执行后面的逻辑，也就是说这一瞬间，并没有通过主线程加载这个资源。等到新线程的资源加载完毕之后会方法一个公共的内存区，在主线程这边检测这个资源加载完毕，把他取出来进行使用即可

## 核心概念

> 同步加载大资源时，读取硬盘数据到内存会占用主线程，资源越大耗时越长，造成游戏**卡顿、掉帧**。
> 
> **Resources 异步加载**：Unity 内部新开子线程加载资源，**不阻塞主线程**，界面不会卡死。 
> ⚠️重要：异步加载不能立刻拿到资源，**至少要等待一帧**，不能执行完`LoadAsync`就直接使用`asset`。

## 异步加载 API
```csharp
ResourceRequest rq = Resources.LoadAsync<Texture>("Tex/Monesy");
```
返回值：`ResourceRequest`，继承自`AsyncOperation`

| 成员            | 说明                          |
| ------------- | --------------------------- |
| `rq.asset`    | 加载完成后才能获取到的资源对象，未完成时不可用     |
| `rq.isDone`   | bool，资源是否加载完成               |
| `rq.progress` | 0‑1 加载进度，**精度不高，不适合做精准进度条** |
## 两种异步加载写法
### 方式 1：completed 完成事件监听
```csharp
void Start() 
{ 
	ResourceRequest rq = Resources.LoadAsync<Texture>("Tex/Monesy"); 
	//注册加载完成回调 
	rq.completed += LoadOver; 
} 

private void LoadOver(AsyncOperation rq) 
{ 
	Debug.Log("加载结束"); 
	//强转为ResourceRequest再取asset 
	Texture tex = (rq as ResourceRequest).asset as Texture; 
}
```
✅优点：代码简洁 
❌缺点：只能加载结束后处理逻辑；适合简单的**线性加载**

### 方式 2：协程 + ResourceRequest
```csharp
IEnumerator Load()
{
    ResourceRequest rq = Resources.LoadAsync<Texture>("Tex/Monesy");
    
    //写法A：直接yield return rq；Unity自动等待加载完成再往下执行
    //yield return rq;
    //Texture tex = rq.asset as Texture;

    //写法B：while循环手动监听进度，可更新进度条UI
    while (!rq.isDone)
    {
        Debug.Log(rq.progress); //打印加载进度
        yield return null; //等到下一帧再回来循环判断
    }
    //加载完成获取资源
    Texture tex = rq.asset as Texture;
}
```
调用：`StartCoroutine(Load());`

✅优点：

1. 可以实时获取加载进度
2. 方便同时管理多个资源加载，适合**并行加载** 
3. ❌缺点：代码写法相对繁琐

> 协程原理：遇到`yield return`暂停后续代码，协程调度器根据返回值决定什么时候继续往下执行。

## 关键易错点总结

1. ❌错误：调用`LoadAsync`之后马上使用`rq.asset`，此时资源还没加载完成，得到 null。
2. 异步加载是子线程干活，但**资源对象的使用、UI 赋值必须回到主线程**（回调、协程都跑在主线程，可放心使用）。
3. `progress`进度值并不精准，不要拿来做高精度进度 UI。
4. `yield return rq;`：Unity 识别到返回 ResourceRequest，会自动等待资源加载完毕才执行后续代码。