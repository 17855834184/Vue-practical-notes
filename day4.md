如果发现某一个组件在项目当中多个地方出现频繁的使用
咱们经常把这类的组件注册为全局组件。
注册全局组件的好处是什么那：只需要注册一次，可以在程序任意地方使用
全局组件放置于components里面



组件name属性的作用?
1开发者工具中可以看见组件的名字
2注册全局组件的时候，可以通过组件实例获取相应组件的名字




三级联动组件知道谁在用它。
    组件在哪一个模块中【home、search】，通过$route路由信息区分


路由跳转的时候，相应的组件会把重新销毁与创建----【kepp-alive】





4)过渡效果
Vue当中也有过渡动画效果---transition内置组件完成
节点|组件务必出现v-if|v-show指令才可以使用。




5)TypeNav三级联动性能优化?

频繁地向服务器发请求，因此咱们需要进行优化。

为什么?
dispatch发送请求写在TypeNav中的mounted,
频繁地加载TypeNav加载就会频繁触发dispatch发送请求

最终解决方案：dispatch写在App.



如果页面中本来就存在params
 location.params = this.$route.params;
      






mock数据。

http://mockjs.com/  官方地址

mock官网一句话：晚上练习的时候，如果网速可以，看看mock的官网，看看语法规则；
生成随机数据，拦截 Ajax 请求
mock官网当中这句话的理解：
模拟的数据一般：对象、数组
{
    'a|1-10':'我爱你'
}
拦截ajax请求：请求发布出去【浏览器会进行拦截：笨想，因为服务器】，只是项目当中本地自己玩耍数据。


第一步:安装依赖包mockjs

第二部：在src文件夹下创建一个文件夹，文件夹mock文件夹。

第三步:准备模拟的数据
把mock数据需要的图片放置于public文件夹中！
比如:listContainer中的轮播图的数据
[
   {id:1,imgUrl:'xxxxxxxxx'}, 
   {id:2,imgUrl:'xxxxxxxxx'}, 
   {id:3,imgUrl:'xxxxxxxxx'}, 
]

第四步：在mock文件夹中创建一个server.js文件

import Mock from 'mockjs';
//webpack默认对外暴露的：图片、JSON数据格式
import banner from './banner.json';
import floor from './floor.json';

Mock.mock("/mock/banner",{code:200,data:banner});
Mock.mock("/mock/floor",{code:200,data:floor});
对于webpack当中一些模块：图片、json，不需要对外暴露，因为默认就是对外暴露。

回到入口文件，引入serve.js

在API文件夹中创建mockRequest【axios实例：baseURL:'/mock'】
专门获取模拟数据用的axios实例。



8)swiper基本的使用
main.js
import "swiper/css/swiper.css";

Carousel/index.vue
import Swiper from "swiper";
  <div class="swiper-container" ref="cur">
    <div class="swiper-wrapper">
      <div
        class="swiper-slide"
        v-for="(carousel, index) in list"
        :key="carousel.id"
      >
        <img :src="carousel.imgUrl" />
      </div>
    </div>
    <!-- 如果需要分页器 -->
    <div class="swiper-pagination"></div>

    <!-- 如果需要导航按钮 -->
    <div class="swiper-button-prev"></div>
    <div class="swiper-button-next"></div>
  </div>


      this.$nextTick(() => {
          var mySwiper = new Swiper(this.$refs.cur, {
            loop: true,
            // 如果需要分页器
            pagination: {
              el: ".swiper-pagination",
              //点击小球的时候也切换图片
              clickable: true,
            },
            // 如果需要前进后退按钮
            navigation: {
              nextEl: ".swiper-button-next",
              prevEl: ".swiper-button-prev",
            },
          });
        });




























































