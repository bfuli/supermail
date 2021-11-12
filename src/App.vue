<template>
  <div id="app">
      <router-view></router-view>
      <tab-bar>
          <tab-bar-item :path="require('@/assets/img/tabbar/首页.svg')"
                        :path-active="require('@/assets/img/tabbar/首页active.svg')"
                        link="/home">首页
          </tab-bar-item>
          <tab-bar-item :path="require('@/assets/img/tabbar/分类.svg')"
                        :path-active="require('@/assets/img/tabbar/分类active.svg')"
                        link="/category">分类
          </tab-bar-item>
          <tab-bar-item :path="require('@/assets/img/tabbar/购物车.svg')"
                        :path-active="require('@/assets/img/tabbar/购物车active.svg')"
                        link="/cart">购物车
          </tab-bar-item>
          <tab-bar-item :path="require('@/assets/img/tabbar/我的.svg')"
                        :path-active="require('@/assets/img/tabbar/我的active.svg')"
                        link="/profile"
                        active-color="#1296db">我的
          </tab-bar-item>
      </tab-bar>
  </div>
</template>

<style>
@import "assets/css/normalize.css";
</style>
<script>
import TabBar from "@/components/tabbar/TabBar";
import TabBarItem from "@/components/tabbar/TabBarItem";
export default {
    name:'App',
    components: {TabBarItem, TabBar}
}
</script>