<!--
 * @Author: your name
 * @Date: 2021-01-21 14:50:15
 * @LastEditTime: 2021-01-25 10:30:05
 * @LastEditors: Please set LastEditors
 * @Description: In User Settings Edit
 * @FilePath: \vue-swiper\src\App.vue
-->
<template>
  <div id="app">
    <div id="nav">
      <!-- <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link>
    </div>
    <router-view/> -->
      <swiper></swiper>
    </div>
  </div>
</template>

<script>
import Swiper from "./views/Swiper.vue";
export default {
  components: { Swiper },
  name: "App",
};
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;

  a {
    font-weight: bold;
    color: #2c3e50;

    &.router-link-exact-active {
      color: #42b983;
    }
  }
}
*{
  padding: 0;
  margin: 0;
}
</style>
