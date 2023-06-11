<template>
  <div id="app-container">
    <h1>App 根组件</h1>
    <hr>

    <button @click="comName = 'Left'">展示Left</button>
    <button @click="comName = 'Right'">展示Right</button>
    <div class="box">
      <!-- 渲染Left组件和Right组件 -->
      <!-- 1.component 标签 是 vue内置的， 作用： 组件的占位符 -->
      <!-- 2.is属性的值，表示要渲染的组件的名字 -->
      <!-- 3. is属性的值，应该是组件在 components 节点下的注册名称 -->
      
      <!-- keep-alive可以吧内部的组件进行缓存，而不是销毁组件 -->

      <!-- include后面应为注册名称  exclude的意思是谁不被缓存 ,注意不要同时使用include，exclude两个属性-->
      <!-- <keep-alive include="Left,Right"> -->
      <keep-alive exclude="Right">
        <component :is="comName"></component>
      </keep-alive>
      

    </div>
  </div>
</template>

<script>
import Left from './components/Left.vue'
import Right from './components/Right.vue'

export default {
  data() {
    return {
      comName: 'Left'
    }
  },
  name: 'App',
  components: {
    //如果在声明组件的时候，没有为组件指定 name（组件的name属性）名称，则组件的名称默认就是"注册时候的名称"
    // 此时组件的名称是MyRight,上面的缓存会失效
    Left,
    Right   
  }
}
</script>

<style lang="less">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.box {
  display: flex;
}
</style>
