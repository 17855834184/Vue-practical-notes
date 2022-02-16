函数参数如果必需要有，可以使用默认参数fun(a=1){...}


Object.assign是浅复制，无法完全复制内部的数据

[...a]也是潜复制

vuex的getters是为了简化state的数据


当前页面的跳转，通过watch监听数据的变化来发送请求


学会套路最重要:
套路1:路由自己跳自己，不会触发mounted----修改路由
套路2：watch监听路由的变化发请求

服务器参数说明是可有可无的，如果把参数设置为undefind可以不传递给服务器，可以优化网络

兄弟组件之间通信用$bus比较好，用vuex可能会破坏原来的结构

子传父组件通信，用事件注册的方法，$on,$emit

父传子组件通信，用属性绑定的方法通信

//删除面包屑的关键字
    removeKeyword() {
      //给服务器带的参数searchParams的keyword置空
      this.searchParams.keyword = undefined;
      //再次发请求
      this.getData();
      //通知兄弟组件Header清除关键字
      this.$bus.$emit("clear");
      //进行路由的跳转
      if (this.$route.query) {
        this.$router.push({ name: "search", query: this.$route.query });
      }
    }


























