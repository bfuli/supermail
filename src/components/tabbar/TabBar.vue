<template>
  <div id="tab-bar">
    <slot></slot>
  </div>
</template>

<script>
export default {
  name: "TabBar"
}
</script>

<style scoped>
#tab-bar{
  /*让所有弹性盒模型对象的子元素都有相同的长度*/
  display: flex;
  background-color: #f6f6f6;
  height: 49px;
  position: fixed;
  left: 0;
  right: 0;
  bottom: 0;
  box-shadow: 0 -1px 1px rgba(100,100,100,0.2);
}
</style>
