<template>
  <div id="app">
    <!-- <img alt="Vue logo" src="./assets/logo.png" />
    <HelloWorld msg="Welcome to Your Vue.js App" /> -->
    <Header/>
    <Main/>
  </div>
</template>

<script>
// import HelloWorld from "./components/HelloWorld.vue";
import Main from '@/components/Main.vue'
import Header from '@/components/Header.vue'

export default {
  name: "App",
  components: {
    Main,
    Header,
  },
};
</script>

<style lang="scss">
@import '@/style/common.scss'
// #app {
//   font-family: Avenir, Helvetica, Arial, sans-serif;
//   -webkit-font-smoothing: antialiased;
//   -moz-osx-font-smoothing: grayscale;
//   text-align: center;
//   color: #2c3e50;
//   margin-top: 60px;
// }
</style>
