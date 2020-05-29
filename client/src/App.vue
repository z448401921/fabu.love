<!--
 * @Author: ainuo
 * @Date: 2020-05-29 14:37:43
 * @LastEditTime: 2020-05-29 15:17:26
 * @FilePath: /fabu.love/client2/src/App.vue
--> 
<template>
  <div id="app">
    <meta
      name="viewport"
      content="width=device-width, initial-scale=1, maximum-scale=1, user-scalable=no"
    >
    <router-view />
  </div>
</template>

<script>
  import {getUserInfo} from './mgr/userMgr'

  export default {
    name: 'App',
    components: {
    },
    data() {
      return {
      }
    },
    created() {
     // console.log(window.location.pathname)
      this.$nextTick(() => {
        let user = getUserInfo()
        if (!user) {
          if (window.location.pathname === '/login' || window.location.pathname === '/') {
            this.$router.push('/login')
          }
        }
      })
    },
    methods: {
    }
  }
</script>
<!-- 引入组件库 -->
<style lang="scss">
  @import "common/scss/reset";
  @import "common/scss/element";
  @import 'common/scss/icon.css';

  #app {
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    color: #2c3e50;
  }
  body {
    background-color: white;
  }
</style>
