### 从零开始搭建 Vue  后管项目

### 一、创建项目

1. 使用 vue-cli 脚手架创建，执行命令：

```shell
vue create `project-name`
```

2. 选择 vue 版本，自动下载依赖，下载完毕，项目创建成功
3. 执行 `npm run serve`，验证项目能否正常启动

### 二、集成

1. vue-router

   路由

   ```
   // 默认安装最新版，vue2 对应的版本为 ue-router3
   npm i vue-router@3 -S
   ```

2. element-ui

   ```
   npm i element-ui -S
   ```

3. axios

   网络请求

   ```
   npm i axios -S
   ```

4. vuex

   状态管理

   ```
   // 默认安装最新版，vue2 对应的版本为 vuex3
   npm i vuex@3 -S
   ```

### 三、引入

1. 编辑 main.js

   ```
   import Vue from 'vue'
   import ElementUI from 'element-ui'
   import 'element-ui/lib/theme-chalk/index.css'
   import App from './App.vue'
   
   // 启动时，生产环境是否显示提示信息
   Vue.config.productionTip = false
   
   // 导入 Element-UI
   Vue.use(ElementUI)
   
   // 导入 store
   import store from './store'
   // 导入路由
   import router from './router'
   
   import '@/permission'
   
   new Vue({
     render: h => h(App),
     router,
     store
   }).$mount('#app')
   ```

   

   

