<template>
  <div class="Left-container">
    <h3>Left组件 --- {{ count }}</h3>
    <button @click="count += 1">+1</button>
  </div>
</template>

<script>
export default {
    data() {
        return {
            count: 0
        }
    },
    created() {
        console.log('Left组件被创建了');
    },
    destroyed() {
        console.log('Right组件被销毁了');
    },
    // 当组件第一次被创建的时候，既会执行 created 生命周期，也会执行 activated 生命周期
    // 当组件被激活的时候，只会触发activated生命周期，不再触发created。因为组件没有被重新创建
    
    activated() {
        console.log('组件被激活了');
    },
    deactivated() {
        console.log('组件被缓存了');
    }
}
</script>

<style>
.Left-container {
    flex: 1;
    height: 500px;
    margin: 0 10px;
    padding: 0 10px 0 10px;
    background-color: orange;
}
</style>