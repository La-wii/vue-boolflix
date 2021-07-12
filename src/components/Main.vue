<template>
    <main>
        <div class="container-lg">

            <div class="search">
                <div class="row">
                    
                </div>
            </div>

            <div class="row py-5">
                <div class="col-12 d-flex flex-wrap py-5">
                    <div v-for="(element, index) in films" :key="index" class="card" style="width: 12rem;">
                        <!-- <img :src="" class="card-img-top" alt="..."> -->

                        <div class="card-body">
                            <h5 class="card-title">
                                {{element.title}}
                            </h5>
                            <p class="card-text">
                                {{element.original_title}}
                            </p>
                            <p class="card-text">
                                {{element.original_language}}
                            </p>
                            <p class="card-text">
                                {{element.vote_average}}
                            </p>
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
            apiURL : "https://api.themoviedb.org/3/movie/popular?api_key=e074c01e562b214f49b0d0b915aa74f1",
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
                this.films = picker.data.results
                
            })
        }
    }

}
</script>

<style scoped lang="scss">
    main{
        background-color: red;
        // height: 1000px;
            .container-lg{
                .search{
                    .row{
                        .col-3{
                            input{

                            }
                            button{
                                
                            }
                        }
                    }
                }
                .row{

                    .col-12{

                        .card{
                        width: calc(100% / 5);
                        margin: 20px;
                        }
                    }
                }
            }
        }
</style>