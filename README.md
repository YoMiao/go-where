# 介绍

> 一个模仿去哪儿旅行的web应用
> 一个简单的学习用的实践

## 记录

用 vue-awesome-swiper 和  better-scroll 组件  
用 fastclick 库解决物理点击和 click 在移动浏览器上触发事件之间300毫秒的延迟。  
每个页面都在入口index的时候通过ajax一次性获取数据，再通过props传入组件，这样可以减少ajax请求。  
由于better-scroll组件会默认禁止click事件，在移动端会产生bug，所以要加上click:true配置参数。  

## 演示

!['演示'](https://raw.githubusercontent.com/YoMiao/go-where/master/screenshots/go-where.gif)

## 测试运行

``` bash
# install dependencies
npm install

# serve with hot reload at localhost:8080
npm run dev

# build for production with minification
npm run build

# build for production and view the bundle analyzer report
npm run build --report
```

<!-- For a detailed explanation on how things work, check out the [guide](http://vuejs-templates.github.io/webpack/) and [docs for vue-loader](http://vuejs.github.io/vue-loader). -->
