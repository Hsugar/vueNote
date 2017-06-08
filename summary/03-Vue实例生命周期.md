## 生命周期

Vue实例运行的整个流程

[http://cn.vuejs.org/v2/guide/instance.html#search-query-sidebar](http://cn.vuejs.org/v2/guide/instance.html#search-query-sidebar)



![](https://ws1.sinaimg.cn/large/006tNbRwly1fg3t7dou4xj30xc25sdko.jpg)





#### beforeCreate

创建之前



#### created

创建之后

```javascript
created () { // 发起网络请求
    console.log('created');
}
```



#### beforeMount

渲染完成之前



#### mounted

渲染完成之后

```javascript
mounted () { // 页面渲染完成
    console.log('mounted');
}
```



#### beforeUpdate

更新之前



#### updated

更新之后



#### beforeDestroy

释放之前



#### destroyed

释放之后





代码示例：

```javascript
beforeCreate () {
    console.log('beforeCreate');
},
created () {
    console.log('created');
},
beforeMount () {
    console.log('beforeMount');
},
mounted () {
    console.log('mounted');
},
beforeUpdate () {
    console.log('beforeUpdate');
},
updated () {
    console.log('updated');
},
beforeDestroy () { // 调用$destroy()方法便会执行
    console.log('beforeDestroy');
},
destroyed () {
    console.log('destroyed');
}
```

