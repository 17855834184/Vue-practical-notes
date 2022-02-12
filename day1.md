
3)脚手架下载下来的项目稍微配置一下
3.1:浏览器自动打开
        在package.json文件中
        "scripts": {
         "serve": "vue-cli-service serve --open",
          "build": "vue-cli-service build",
          "lint": "vue-cli-service lint"
        },


3.2关闭eslint校验工具
创建vue.config.js文件：需要对外暴露
module.exports = {
   lintOnSave:false,
}

3.3 src文件夹的别名的设置

创建jsconfig.json文件
{
    "compilerOptions": {
        "baseUrl": "./",
        "paths": {
            "@/*": [
                "src/*"
            ]
        }
    },
    "exclude": [
        "node_modules",
        "dist"
    ]
}

路由重定项
 {
    path:"*",
    redirect:'/home'
  },

1：安装less less-loader 版本不是固定的，官方在升级，不同版本之间的依赖不同

2:需要在style标签的身上加上lang="less",不添加样式不生效

插件的使用一定要 new VueRouter，刚刚不写找了好久的错误

刚刚npm i vue-router 居然报错了，
因为官方的vue-router版本升级，vue和vue-router之间有依赖关系，
给vue-router降了一个版本就成功了

结论：多看报错日志，通常安装不上就降版本

7)路由的跳转
路由的跳转就两种形式：声明式导航（router-link：务必要有to属性）
                    编程式导航push||replace
编程式导航更好用：因为可以书写自己的业务逻辑

this.$route是存在页面上的，不是存在单个组件的，所以都能获取






9）路由传参
params参数：路由需要占位 path:'/home/:keyword'
query参数

路由传递参数先关面试题
     1:路由传递参数（对象写法）path是否可以结合params参数一起使用?
     不可以：不能这样书写，程序会崩掉

     2:如何指定params参数可传可不传? 
     加个问号   path:'/home/:keyword?'

     3:params参数可以传递也可以不传递，但是如果传递是空串，如何解决？
        params:{keyword:''||undefind}
   
     5: 路由组件能不能传递props数据?
     基础的vue教学里面有
     




















     
    


