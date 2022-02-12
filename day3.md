
8)函数防抖与节流*******面试题

正常：事件触发非常频繁，而且每一次的触发，回调函数都要去执行（如果时间很短，而回调函数内部有计算，那么很可能出现浏览器卡顿）

防抖：前面的所有的触发都被取消，最后一次执行在规定的时间之后才会触发，也就是说如果连续快速的触发,只会执行最后一次
_.debounce(func, [wait=0], [options=])

节流：在规定的间隔时间范围内不会重复触发回调，只有大于这个时间间隔才会触发回调，把频繁触发变为少量触发

import {throttle} from "lodash";

  changeIndex: throttle(function(index) {
      //函数节流:在20MS时间之内只能执行一次
      this.currentIndex = index;
    }, 20),




9)优化项目。
1 v-if|v-show
2 函数防抖与节流
3 按需加载:对于loadsh插件，它里面封装的函数功能很多
import _ from lodash 相当于把全部功能引入进来，但是我们只是需要节流。
所以可以这样
import {throttle} from "lodash";




为什么使用router-link组件的时候，会出现卡顿那？
v-for遍历出很多的router-link
router-link是一个组件：相当于VueComponent类的实例对象，一瞬间
new VueComponent很多实例（1000+），很消耗内存，因此导致卡顿。
所以使用编程式导航 this.$router.push()














































