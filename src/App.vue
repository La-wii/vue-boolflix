<template>
  <div id="app">
    <!-- <Header/> -->
    <Search @search="search"/>
    <Main :films="films" :serie="serie"/>
  </div>
</template>

<script>
import axios from 'axios';
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
      selectionText: '',
      films: [],
      serie: [],

      aUrlF:'https://api.themoviedb.org/3/search/movie',
      aKeyF:'e23f5b7ea0860eb65056406dfeb3eda9',
      language: 'it-IT',
      aUrlS:'https://api.themoviedb.org/3/search/tv',
      
    }
  },
  methods: {
    // search(str){
    //   console.log(str);
    //   this.selectionText = str;
    // },

    search(text){
            axios
            .get(this.aUrlF, {
                params: {
                    api_key: this.aKeyF,
                    language: this.language,
                    query: text
                }
            })

            
            .then (picker =>{
                
                this.films = picker.data.results;
                console.log(this.films);
            });

            axios
            .get(this.aUrlS,{
              api_key: this.aKeyF,
              language: this.language,
              query: text
            })

            .then (discover =>{
                
              this.serie = discover.data.results
              console.log(this.serie);
                
            });
        },

      }
    }

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
