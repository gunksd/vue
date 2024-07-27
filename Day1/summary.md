1.ref 返回的如果哦是字符串要加''
2.在set up里面定义的响应式方法是不需要暴露的，直接就可以在模版中使用。
3.reactive的对象在模版中是不能像ref那样直接引用的。
 比如定义的counter里面有一个count，就在模版中要用counter.count才能使用。
