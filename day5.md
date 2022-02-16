



初始化swiper实例之前，页面中的节点（结构）务必要有，

1.4动态效果为什么没有出来？
1数据的获取是异步操作，2数据更新之后不能马上获取dom,要等mounted运行结束，


1数据的获取是异步操作
第一种解决方案，延迟器（不是完美的解决方案）

第二种解决方案，watch:监听属性

第三种方法 promise.then可以解决异步操作问题，或者async await 配合promise


2数据更新之后不能马上获取dom
组件实例的一个方法:$nextTick
this.$nextTick(()=>{

})
dom更新循环结束之后再执行nextTick这个回调
修改数据之后 立即使用这个方法，获取更新后的DOM。



3)开发Floor组件
父组件获取到mock数据，通过v-for遍历 生成多个floor组件，因此达到复用作用。

3.4组件间通信******面试必问的东西
props:父子
插槽:父子
自定义事件:子父
全局事件总线$bus:万能
pubsub:万能
Vuex:万能
$ref:父子通信

为什么在Floor组件的mounted中初始化SWiper实例轮播图可以使用.

 Floor组件来自v-for的遍历,
 v-for完成才会渲染组件
 v-for遍历必须有一个完整的数据，
 v-for会等待数据的返回



4)carousel全局组件
如果项目当中出现类似的功能，且重复利用，封装为全局组件








































