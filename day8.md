经典面试题：v-for与v-if优先级？ v-for优先级更高

push与replace区别?
编程式导航：push 与 replace
能不能记录历史记录：push（能记住历史记录）  replace（不能记住历史记录）


滚动行为的设置。

let router = new VueRouter({

  //滚动行为
  scrollBehavior(to, from, savedPosition) {
    //返回的这个y=0，代表的滚动条在最上方
    return { y: 0 };
  },
});
