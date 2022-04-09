QFuture

QFuture 用来获取异步计算的结果，用于多线程的同步

QFuture 保存有计算结果的返回值，返回值可以是有构造函数和赋值构造函数的任何类型

结果可以通过函数
result()
resultAt()
results()
获取。如果获取时，异步计算还未完成，将会阻塞至异步计算结果完成

QFuture 可以保留多份连续的结果？

计算可以被取消。可以被暂停并恢复
注意：Concurrent::run()启动的线程不能被取消或者停止

QFuture waitForFinished()，阻塞等待异步计算完成

QFuture是比较轻量级的，可以通过传值来进行传递

## QtConcurrent::mappedReduced()
mappedReduced()跟mapped()函数差异不大，多了一个参数，会把每个结果值，当作参数，放入新的函数中
执行并得出新的结果值。
新函数的格式为
void newFunc(int &result, const int & intermediate)
结果值就保存于result中,可通过future.result()来获取

可以指定新函数的执行规则
QtConcurrent::UnorderedReduce
QtConcurrent::OrderedReduce
