Rxjava
===

### 一. 是什么?
处理异步事件的一个库
RxJava is a Java VM implementation of ReactiveX (Reactive Extensions): a library for composing asynchronous and event-based programs by using observable sequences

关键词   composing asynchronous 、event-based 、observable sequences

### 二. 有什么用，优点
逻辑简洁

no callback
no care Thread
can reuse common operations

#### 三. 同样是处理异步事件 ，和 AsyncTask、 Handler、 Loaders 、Android Annotations、EventBus对比有什么优点

How to execute heavy tasks on background threads and deliver result(or error)in ui thread?
*. Handler结合Thread   handler.post handler.sentmessage...
优点：熟悉，书写简单
缺点：
*. AsyncTask
优点：书写简单
缺点：没有结合activity/fragment的生命周期；不可嵌套组合

*. Loaders
优点：结合activity/fragement的生命周期
缺点：不可嵌套组合
*. EventBus
*. Rxjava
Functional Reactive Programming 函数响应式编程
### 四. 概念，名词
Rxjava采用的是一种扩展的观察者模式，和标准的观察者模式有一点区别：


it differs in one key way - Observables often don't start emitting items until someone explicitly subscribes to them 


(4.1) Observables: 被观察的对象/发布者

(4.2) Subscriber、Observer:观察者/订阅者
(4.3) subscription:interface 订阅，取消订阅
(4.4) subscribe： 
上述关系汇总如下：

subscription = observable.subscibe(subsciber)

subscription.unsubscribe()
另外：
通过subscribeon(Scheduler.io())指定被观察者执行的线程
observeOn(AndroidSechedules.mainThread()) 观察者执行的线程

#### (4.5) Observable create
*. create()
*. just()
*. join()
*. from()

#### (4.6) Observable transformation 转换
*. map
![](https://github.com/Netflix/RxJava/wiki/images/rx-operators/map.png)
filit
*. flatMap()
![](https://github.com/Netflix/RxJava/wiki/images/rx-operators/mapMany.png)
*. scan()
![](https://github.com/Netflix/RxJava/wiki/images/rx-operators/scan.png)
*. groupuBy()
![](https://github.com/Netflix/RxJava/wiki/images/rx-operators/groupBy.png)
*. buffer()
![](https://github.com/Netflix/RxJava/wiki/images/rx-operators/buffer.png)
*. window()


#### (4.7) Observable filtering 过滤
*. filter()
![](https://github.com/Netflix/RxJava/wiki/images/rx-operators/filter.png)
*. skip()
![](https://github.com/Netflix/RxJava/wiki/images/rx-operators/skip.png)
*. take()
![](https://github.com/Netflix/RxJava/wiki/images/rx-operators/take.png)
*. takeLast

*. takeLastBuffer()
*. first()
*. elementAt()
*. timeout()
![](https://github.com/Netflix/RxJava/wiki/images/rx-operators/timeout.1.png)
*. distinct()
![](https://github.com/Netflix/RxJava/wiki/images/rx-operators/distinct.png)
*. distinctUntilChanged
![](https://github.com/Netflix/RxJava/wiki/images/rx-operators/distinctUntilChanged.png)

#### (4.8) Subscirber 回调
*. Subscriber [onNext;onCompleted;onError]
*. Action [only onNext]

### 五. 如何使用
#### (5.1) 创建 Observables
*. 通过just()、from()等操作把已有的数据结构(objects,lists,arrays...)创建Observable
subscriber将会同步的调用onNext() 直到onCompleted() or onError()
*. 通过[create()](http://reactivex.io/documentation/operators/create.html)方法创建一个Observable
 
#### (5.2) 用Operators处理Observables【中间处理eg: skip()、 take()、 map() ...】
chain operators 链式操作



#### (5.3) 错误处理
onError()
onErrorResumeNext()
onErrorReturn()

### 六. 情景分析


[ 可能是东半球最全的RxJava使用场景小结](http://blog.csdn.net/theone10211024/article/details/50435325)


### 七. demo


### 八. 疑问

### 九. 参考
1. [给 Android 开发者的 RxJava 详解](给 Android 开发者的 RxJava 详解)
2. [the official RxJava wiki](https://github.com/ReactiveX/RxJava/wiki)
3. Grokking RxJava, [Part 1: The Basics](http://blog.danlew.net/2014/09/15/grokking-rxjava-part-1/), [Part 2: Operator, Operator](http://blog.danlew.net/2014/09/15/grokking-rxjava-part-1/), [Part 3: Reactive with Benefits](http://blog.danlew.net/2014/09/15/grokking-rxjava-part-1/), [Part 4: Reactive Android](Grokking RxJava, Part 1: The Basics, Part 2: Operator, Operator, Part 3: Reactive with Benefits, Part 4: Reactive Android - published in Sep/Oct 2014 by Daniel Lew) - published in Sep/Oct 2014 by Daniel Lew
4. [FRP on Android](http://slides.com/yaroslavheriatovych/frponandroid)

### 十. 推荐
[Awesome-RxJava](https://github.com/lzyzsd/Awesome-RxJava)
[RxJava文档中文版](https://mcxiaoke.gitbooks.io/rxdocs/content/)
### 优秀的Rxjava开源项目
1. [RxJava-Android-Samples](https://github.com/kaushikgopal/RxJava-Android-Samples)
2. [Meizhi](https://github.com/drakeet/Meizhi)
