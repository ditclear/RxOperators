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

>###Take

	emit only the first n items emitted by an Observable

	只取开头的几个元素

>###TakeLast

	emit only the last n items emitted by an Observable

	只取结尾的几个元素
	
>###Distinct

	suppress duplicate items emitted by an Observable

	去掉重复的元素
	
>###DistinctUntilsChanged

	suppress duplicate items emitted by an Observable

	忽略掉所有的重复并且只发射出新的值

>###Skip

	suppress the first n items emitted by an Observable

	创建一个不发射前n个元素而是发射它后面的那些数据的Observable

>###SkipLast

	suppress the final n items emitted by an Observable

	创建一个跳过后面n个元素从源序列中发射剩下的其他元素的Observable	
	
>###ElementAt

	emit only item n emitted by an Observable

	仅从一个序列中发射第n个元素
	
>###Sample

	emit the most recent items emitted by an Observable within periodic time intervals
	
	创建一个新的可观测序列，它将在一个指定的时间间隔里由Observable发射最近一次的数值
	
>###Timeout

	mirror the source Observable, but issue an error notification if a particular period of time elapses without any emitted items
	
	如果在指定的时间间隔内Observable不发射值的话，它监听的原始的Observable时就会触发onError()函数
	
>###Debounce

	only emit an item from an Observable if a particular timespan has passed without it emitting another item
	
	过滤掉由Observable发射的速率过快的数据；如果在一个指定的时间间隔过去了仍旧没有发射一个，那么它将发射最后的那个
	
>###Scan

	apply a function to each item emitted by an Observable, sequentially, and emit each successive value

	scan()函数可以看做是一个累加器函数。scan()函数对原始Observable发射的每一项数据都应用一个函数，它将函数的结果填充回可观测序列，等待和下一次发射的数据一起使用

给出一个累加器：

	Observable.just(1,2,3,4,5)
        .scan((sum,item) -> sum + item)
        .subscribe(new Subscriber<Integer>() {
            @Override
            public void onCompleted() {
                Log.d("RXJAVA", "Sequence completed.");
            }
 
            @Override
            public void onError(Throwable e) {
                Log.e("RXJAVA", "Something went south!");
            }
 
            @Override
            public void onNext(Integer item) {
                Log.d("RXJAVA", "item is: " + item);
            }
        });
        
我们得到的结果是：
        
	RXJAVA: item is: 1
	RXJAVA: item is: 3
	RXJAVA: item is: 6
	RXJAVA: item is: 10
	RXJAVA: item is: 15
	RXJAVA: Sequence completed.

>###GroupBy

	divide an Observable into a set of Observables that each emit a different group of items from the original Observable, organized by key

	将源Observable变换成一个发射Observables的新的Observable。它们中的每一个新的Observable都发射一组指定的数据
	
>###Buffer

	periodically gather items from an Observable into bundles and emit these bundles rather than emitting the items one at a time

	将源Observable变换一个新的Observable，这个新的Observable每次发射一组列表值而不是一个一个发射

>###Window

	periodically subdivide items from an Observable into Observable windows and emit these windows rather than emitting the items one at a time

	window()函数和buffer()很像，但是它发射的是Observable而不是列表
	
	这些Observables中的每一个都发射原始Observable数据的一个子集，数量由count指定,最后发射一个onCompleted()结束

>###Cast

	transform the items emitted by an Observable by applying a function to each item

	它是map()操作符的特殊版本。它将源Observable中的每一项数据都转换为新的类型，把它变成了不同的Class

	
	
	
	
