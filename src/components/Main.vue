<template>
    <main>
        <div class="container-lg">

            <div class="search">
                <div class="row">

                    <div class="col-4 py-3 d-inline-flex">
                        <input type="text" 
                        class="form-control" 
                        placeholder="Scegli un titolo"
                        v-model.trim="inputText">

                        <button type="submit" class="ms-2 px-2">Cerca</button>
                    </div>
                    
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
            inputText:'',
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
                
                // this.films = picker.data.title
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