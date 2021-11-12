<template>
<div class="tab-bar-item" @click="click">
  <img :src="src"/>
  <div :style="activeStyle">
    <slot></slot>
  </div>
</div>
</template>

<script>
export default {
  name: "TabBarItem",
  data(){
    return {
      src:''
    }
  },
  props: {
    path: {//表示图标的默认地址，也就是未选中状态下的图片链接
      type: String,
      required: true
    },
    pathActive:{//表示图标激活之后的图片地址
      type: String,
      required: false
    },
    link:{//相对路径：表示点击当前tab，需要跳转到的连接
      required:true
    },
    activeColor:{//tab激活之后字体颜色
      type:String,
      default:'red'
    }
  },
  computed:{
    //计算属性，表示当前tab是否激活，之后是否改变tab图标和字体颜色，依赖该属性
    isActive(){
      // return this.$route.path.indexOf(this.link) != -1
      return this.$route.path === this.link
    },
    activeStyle(){
      return this.isActive ? {color:this.activeColor}:{}
    }
  },
  methods:{
    //点击不同tab，跳转不同链接
    click(){
      if (this.$route.path != this.link) this.$router.replace(this.link)
    }
  },
  mounted() {//初始化图标的地址，默认未选中状态
    this.src = this.path
    if (this.pathActive === undefined) this.pathActive = this.path
  },
  updated() {//每次isActive更新之后，改变图标的地址，更新图标
    if (this.isActive){
      this.src = this.pathActive
    }else {
      this.src = this.path
    }
  }
}
</script>

<style scoped>
.tab-bar-item{
  flex: 1;
  text-align: center;
  font-size: 14px;
}
.tab-bar-item img{
  height: 24px;
  width: 24px;
  margin-top: 2px;
  vertical-align: middle;
  margin-bottom: 2px;
}
.active{
  color: red;
}
</style>
