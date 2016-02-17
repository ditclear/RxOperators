###ReactiveX操作符
---

>###Map

	transform the items emitted by an Observable by applying a function to each item

	用来把一个事件转换为另一个事件。
	map()操作符就是用于变换Observable对象的，map操作符返回一个Observable对象，这样就可以实现链式调用，在一个Observable对象上多次使用map操作符，最终将最简洁的数据传递给Subscriber对象。

>###From

	convert various other objects and data types into Observables

	from()接收一个集合作为输入，然后每次输出一个元素给subscriber.

>###FlatMap

	transform the items emitted by an Observable into Observables, then flatten the emissions from those into a single Observable

	Observable.flatMap()接收一个Observable的输出作为输入，同时输出另外一个Observable。

>###Filter 

	emit only those items from an Observable that pass a predicate test	

	过滤,把不符合条件的过滤掉,留下符合条件的

>###Just

	create an Observable that emits a particular item

创建一个特定输入的Observable

>###Repeat

	create an Observable that emits a particular item or sequence of items repeatedly

	重复发送

>###Defer

	do not create the Observable until the observer subscribes, and create a fresh Observable for each observer

	声明一个Observable但是你又想推迟这个Observable的创建直到观察者订阅时

>###Range

	create an Observable that emits a range of sequential integers

	从一个指定的数字X开始发射N个数字,range()函数用两个数字作为参数：第一个是起始点，第二个是我们想发射数字的个数。

>###Interval

	create an Observable that emits a sequence of integers spaced by a particular time interval

	创建一个轮询的Observable,interval()函数的两个参数：一个指定两次发射的时间间隔，另一个是用到的时间单位

>###Timer

	create an Observable that emits a single item after a given delay

	一段时间之后才发射的Observable

	timer(3,TimeUnit.SECONDS)

	它将3秒后发射0,然后就完成了

	timer(3,3,TimeUnit.SECONDS)

	
	用这个代码，你可以创建一个以初始值来延迟执行的interval()版本，然后每隔N秒就发射一个新的数字





