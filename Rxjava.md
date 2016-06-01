Rxjava
===

### 是什么?
处理异步事件的一个库
RxJava is a Java VM implementation of ReactiveX (Reactive Extensions): a library for composing asynchronous and event-based programs by using observable sequences

关键词   composing asynchronous 、event-based 、observable sequences

### 有什么用，优点
逻辑简洁

#### 同样是处理异步事件 ，和 AsyncTask Handler EventBus对比有什么优点
????

### 概念，名词
Observables: 被观察的对象/发布者
Subscriber、Observer:观察者/订阅者
subscription:interface 订阅，取消订阅
subscribe：
action
#### Observable transformation 转换
*. map
![](https://github.com/Netflix/RxJava/wiki/images/rx-operators/map.png)
filit
*. flatMap()
*. scan()
*. groupuBy()
*. buffer()
*. window()

#### Observable filtering 过滤
*. filter()
*. takeLast()
*. takeLastBuffer()
*. skip()
*. take()
*. first()
*. elementAt()
*. timeout()
*. distinct()

### 如何使用
#### 创建 Observables
*. 通过just()、from()等操作把已有的数据结构(objects,lists,arrays...)创建Observable
subscriber将会同步的调用onNext() 直到onCompleted() or onError()
*. 通过[create()](http://reactivex.io/documentation/operators/create.html)方法创建一个Observable
 
#### 用Operators处理Observables【中间处理eg: skip()、 take()、 map() ...】
chain operators 链式操作



#### 错误处理
onError()
onErrorResumeNext()
onErrorReturn()
### 情景分析



### demo


### 疑问

### 参考
1. [给 Android 开发者的 RxJava 详解](给 Android 开发者的 RxJava 详解)
2. [ReactiveX/RxJava wiki](https://github.com/ReactiveX/RxJava/wiki)
3. Grokking RxJava, [Part 1: The Basics](http://blog.danlew.net/2014/09/15/grokking-rxjava-part-1/), [Part 2: Operator, Operator](http://blog.danlew.net/2014/09/15/grokking-rxjava-part-1/), [Part 3: Reactive with Benefits](http://blog.danlew.net/2014/09/15/grokking-rxjava-part-1/), [Part 4: Reactive Android](Grokking RxJava, Part 1: The Basics, Part 2: Operator, Operator, Part 3: Reactive with Benefits, Part 4: Reactive Android - published in Sep/Oct 2014 by Daniel Lew) - published in Sep/Oct 2014 by Daniel Lew
4. [FRP on Android](http://slides.com/yaroslavheriatovych/frponandroid)

