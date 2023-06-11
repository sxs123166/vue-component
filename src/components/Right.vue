<template>
  <div class="Right-container">
    <h1>Right组件</h1>
  </div>
</template>

<script>
export default {
    //当提供了name属性之，组件的名称，就是name属性的值
    // 对比：
    // 1. 组件的“注册名称”的主要应用场景是：以标签的形式，把注册好的组件，渲染和使用到页面结构之中
    // 2. 组件声明时候的“name”名称的主要应用场景；结合<keep-alive></keep-alive>标签实现组件缓存的功能，以及在调试工具中看到组件的name名称

    name: 'MyRight'
}
</script>

<style>
.Right-container {
    flex: 1;
    height: 500px;
    margin: 0 10px;
    padding: 0 10px 0 10px;
    background-color: red;
}
</style>