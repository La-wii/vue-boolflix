<template>
    <main>
        <div class="container-lg">
            <div class="row py-5">
                <div class="col-12 d-flex flex-wrap py-5">
                    <div v-for="(element, index) in films" :key="index" class="card" style="width: 18rem;">
                        <!-- <img :src="" class="card-img-top" alt="..."> -->

                        <div class="card-body">
                            <h5 class="card-title">{{element.title}}</h5>
                            <p class="card-text">{{element.original_title}}</p>
                            <p class="card-text">{{element.original_language}}</p>
                            <p class="card-text">{{element.vote_average}}</p>
                        </div>

                    </div>

                </div>
            </div>
             
        </div>
    
    </main>
</template>

<script>
import axios from 'axios';
export default {
    name: "Main",
    data() {
        return {
            apiURL : "https://api.themoviedb.org/3/movie/550?api_key=e23f5b7ea0860eb65056406dfeb3eda9",
            films: [],
        }
    },
    created (){
       this.getFilms() 
       
    },
    methods: {
        getFilms(){
            axios
            .get(this.apiURL)
            .then (picker =>{
                console.log(picker);
                this.films.push(picker.data)
                
                // this.films = picker.data.title
            })
        }
    }

}
</script>

<style scoped lang="scss">
    main{
        background-color: red;

            .row{

                .col-12{

                    .card{
                    width: calc(100% / 5);
                    margin: 20px;
                    }
                }
            }
        }
</style>