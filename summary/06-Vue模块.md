## Vue模块



### vue-router

[http://router.vuejs.org/zh-cn/essentials/getting-started.html](http://router.vuejs.org/zh-cn/essentials/getting-started.html)

1.  安装

    ```
    npm install --save vue-router
    ```

2. 引入

    ```javascript
    import VueRouter from 'vue-router'
    ```

3. Vue安装模块

    ```javascript
    Vue.use(VueRouter)
    ```

4. 一级路由的使用

    ```html
    <router-link to="/home">Home</router-link>
    <router-link to="/cart">Cart</router-link>
    <router-link to="/mine">Mine</router-link>
    <router-view></router-view>
    ```

    引入对应的文件，并编写路由规则

    ```javascript
    import Home from './pages/home'
    import Cart from './pages/cart'
    import Mine from './pages/mine'

    // 定义路由规则
    const routes = [
        { path: '', component: Home },
        { path: '/home', component: Home },
        { path: '/cart', component: Cart },
        { path: '/mine', component: Mine }
    ];

    // 创建路由实例
    const router = new VueRouter({
        routes
    });

    // 挂在在vue实例中
    const app = new Vue({
        el: '#app',
        template: '<App/>',
        components: { App },
        router
    })
    ```

5. 二级路由的使用

    ```html
    <router-link to="/mine/one">One</router-link>
    <router-link to="/mine/two">Two</router-link>
    <router-view></router-view>
    ```

    配置二级路由，其它区域代码不变

    ```javascript
    const routes = [
      { path: '/mine', component: Mine, children: [
          { path: '', component: One },
          { path: 'one', component: One },
          { path: 'two', component: Two },
          { path: 'three', component: Three },
      ] }
    ]
    ```

    ​

    ​



### vue-resource



1.  安装

    ```
    $ npm install --save vue-resource
    ```

2. 引入

    ```javascript
    import VueResource from 'vue-resource';
    ```

3. Vue安装模块

    ```javascript
    Vue.use(VueResource);
    ```

4. 使用

    ```javascript
    // 全局使用
    Vue.http.get('/someUrl', [options]).then(successCallback, errorCallback);
    Vue.http.post('/someUrl', [body], [options]).then(successCallback, errorCallback);

    // 局部使用
    this.$http.get('/someUrl', [options]).then(successCallback, errorCallback);
    this.$http.post('/someUrl', [body], [options]).then(successCallback, errorCallback);
    ```

    通常情况下，都会将网络请求放在`created`方法中

    ```javascript
    created () {
        this.$http.get('url').then(data => {
            // ...
        });
      
        this.$http.post('url').then(data => {
            // ...
        });
      
        this.$http.jsonp('url').then(data => {
            // ...
        });
    }
    ```

5. 其他的方法: [api文档](https://github.com/pagekit/vue-resource/blob/develop/docs/http.md)




