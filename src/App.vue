<template>
  <div id="app">
    <!-- <Header/> -->
    <Search @search="search"/>
    <Main :search="selectionText"/>
  </div>
</template>

<script>
import Main from '@/components/Main.vue'
import Search from '@/components/Search.vue'

export default {
  name: "App",
  components: {
    Main,
    // Header,
    Search,
  },
  data(){
    return{
      selectionText: ''
    }
  },
  methods: {
    search(str){
      console.log(str);
      this.selectionText = str;
    }
  }
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
