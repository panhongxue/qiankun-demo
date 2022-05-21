<template>
  <div id="app">
    <!-- <img alt="Vue logo" src="./assets/logo.png" /> -->
    <a href="/app-vue">/app-vue</a>
    &nbsp; 
    <a href="/app-react">/app-react</a>
    <br><br>
    #container:
    <div id="container" style="border:2px inset #ccc"></div>

    <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
  </div>
</template>

<script>
import { registerMicroApps, start } from 'qiankun';
// import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  components: {
    // HelloWorld
  },

  mounted() {
    console.log('mounted');
    registerMicroApps([
      {
        name: 'vue-app',
        entry: '//localhost:8080',
        container: '#container',
        activeRule: '/app-vue',
      },
      {
        name: 'react-app',
        entry: '//localhost:3000',
        container: '#container',
        activeRule: '/app-react',
      },
    ]);
    // 启动 qiankun
    start();
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  /* margin-top: 60px; */
}
</style>
