<template>
    <main></main>
</template>

<script>
import axios from 'axios';
export default {
    name: "Main",
    data() {
        return {
            apiURL : 'https://api.themoviedb.org/3/movie/550?api_key=e23f5b7ea0860eb65056406dfeb3eda9',
            films: [],
        }
    },
    methods: {
        getSong(){
            axios
            .get(this.apiURL)
            .then (picker =>{
                // console.log(picker);
                this.films = picker.data.response
                console.log(this.fimls);
            })
        }
    }

}
</script>

<style>

</style>