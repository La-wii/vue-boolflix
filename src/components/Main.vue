<template>
    <main>
        <div class="container-lg">
        
            <!-- inizio row -->
            <div class="row py-5">
                <!-- inizio col -->
                <div class="col-12 d-flex flex-wrap py-5">
                    
                    <!-- inizio div ciclo -->
                    <div v-for="(element, index) in films" :key="index" class="card bg-transparent" style="width: 14rem;">

                        <!-- inizio  img + card -->
                        <!-- <img :src="" class="card-img-top" alt="..."> -->
                        <div class="card-body" v-if="element.title.toLowerCase().includes(search.toLowerCase())">
                            <h5 class="card-title">
                                {{element.title}}
                            </h5>
                            <p class="card-text">
                                <strong>Titolo originale:</strong>
                                <br>
                                {{element.original_title}}
                            </p>
                            <p class="card-text">
                                <strong>Lingua originale:</strong>
                                <br>
                                {{element.original_language}}
                                <img :src="'/img/'+element.original_language+'.png'" alt="">
                            </p>
                            <p class="card-text">
                                <strong>Voto:</strong>
                                <br>
                                {{element.vote_average}}
                            </p>
                        </div>
                        <!-- fine img + card -->
                    </div>
                    <!-- fine div ciclo -->
                </div>
                <!-- fine col --> 
            </div>
            <!-- fine row -->


            
            <!-- inizio row -->
            <div class="row py-5">
                
                <!-- inizio col -->
                <div class="col-12 d-flex flex-wrap py-5">
                    
                    <!-- inizio div ciclo -->
                    <div v-for="(element, index) in series" :key="index" class="card bg-transparent" style="width: 14rem;">

                        <!-- inizio  img + card -->
                        <!-- <img :src="" class="card-img-top" alt="..."> -->
                        <div class="card-body" v-if="element.name.toLowerCase().includes(search.toLowerCase())">
                            <h5 class="card-title">
                                {{element.name}}
                            </h5>
                            <p class="card-text">
                                <strong>Titolo originale:</strong>
                                <br>
                                {{element.original_name}}
                            </p>
                            <p class="card-text">
                                <strong>Lingua originale:</strong>
                                {{element.original_language}}
                                <img :src="'/img/'+element.original_language+'.png'" alt="">
                            </p>
                            <p class="card-text">
                                <strong>Voto:</strong>
                                <br>
                                {{element.vote_average}}
                            </p>
                        </div>
                        <!-- fine img + card -->
                    </div>
                    <!-- fine div ciclo -->
                </div>
                <!-- fine col --> 
            </div>
            <!-- fine row -->
        </div>
    
    </main>
</template>

<script>
import axios from 'axios';
export default {
    name: "Main",
    props: {
    search: String,
    },
    data() {
        return {
            apiURL : "https://api.themoviedb.org/3/movie/popular?api_key=e074c01e562b214f49b0d0b915aa74f1",
            films: [],
            serieURL : "https://api.themoviedb.org/3/search/tv?api_key=e99307154c6dfb0b4750f6603256716d&language=it_IT&query=s",
            series: [],
        }
    },
    created (){
       this.getFilms(),
       this.getSeries()
       
    },
    methods: {
        getFilms(){
            axios
            .get(this.apiURL)
            .then (picker =>{
                console.log(picker);
                this.films = picker.data.results
                
            })
        },
        // searchCharacter(searchInput){
        //     this.searchText = searchInput;
            
        // }
        getSeries(){
            axios
            .get(this.serieURL)
            .then (discover =>{
                console.log(discover);
                this.series = discover.data.results
                
            })
        }
    }

}
</script>

<style scoped lang="scss">
    main{
        background-color: red;
        height: 93vh;
        overflow-y: scroll;
            .container-lg{
                .row{

                    .col-12{

                        .card{
                        width: calc(100% / 5);
                        margin: 20px;
                            img{
                                height: 20px;
                                width: 20px;
                                margin-left: 3px;
                            }
                        }
                    }
                }
            }
        }
</style>