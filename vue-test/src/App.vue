<template>
  <div id="app">
    <img src="./assets/logo.png">
    <router-view/>
    <!-- <Fine></Fine>-->
    <Math2 :reportName="greeting" :url="greeting"></Math2>
    <Child psMsg="父传子的内容:12344" @transfer="getUser"></Child>  <!--绑定自定义事件transfer-->
    <Child psMsg="父传子的内容:234456" @transfer2="getUser2"></Child>
  </div>
</template>

<script>
// 引入组件以使用：<Math2></Math2>
import Fine from './components/Fine.vue'
import Math2 from './components/Math.vue'
import Child from './components/Child.vue'
export default {
  data () {
    return {
      msg: '欢迎来到菜鸟乐园',
      greeting: '你好',
      user: '',
      userObj: {}
    }
  },
  methods: {
    getUser (obj) {
      console.log('接收从子组件传递过来的值：', obj)
      this.user = obj
    },
    getUser2 (obj) {
      console.log('接收从子组件传递过来的对象', obj)
      this.userObj = obj
    }
  },
  components: {
    Fine,
    Math2,
    Child
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
