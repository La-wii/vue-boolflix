<template>
    <main>
        <div class="container-lg">
        
            <!-- inizio row -->
            <div class="row py-5">
                <h2>Film</h2>
                <!-- inizio col -->
                <div class="col-12 d-flex flex-wrap py-5">
                    
                    <!-- inizio div ciclo -->
                    <div v-for="(element, index) in films" :key="index" class="card bg-transparent" style="width: 13rem;">

                        <!-- inizio  img + card -->
                        <img :src="'https://image.tmdb.org/t/p/w342'+ element.poster_path" alt="" class="position-relative card-img" onerror="this.src='/img/not-found.jpg'">

                        <div class="card-body position-absolute">
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
                                <star-rating :star-size=10 :rating="Math.round((element.vote_average)/2)"></star-rating>
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
                <h2>Serie</h2>
                <!-- inizio col -->
                <div class="col-12 d-flex flex-wrap py-5">
                    
                    <!-- inizio div ciclo -->
                    <div v-for="(element,index) in series" :key="index" class="card bg-transparent" style="width: 13rem;">
 
                        <!-- inizio  img + card -->
                        <img :src="'https://image.tmdb.org/t/p/w342'+ element.poster_path" alt="..." class="position-relative card-img" onerror="this.src='/img/not-found.jpg'">
                        <div class="card-body position-absolute">
                            <h5 class="card-title">
                                {{element.name}}x   
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
                                <star-rating :star-size=10 :rating="Math.round((element.vote_average)/2)" ></star-rating>
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
import StarRating from 'vue-star-rating';
export default {
    name: "Main",
    components: {
    StarRating
    },
    props: {
    films: Array,
    series: Array,
    }       
}   
</script>

<style scoped lang="scss">
    main{
        background-color: black;
        height: 93vh;
        overflow-y: scroll;
            .container-lg{
                .row{

                    .col-12{

                        .card{
                        width: calc(100% / 5);
                        margin: 20px;
                        color: transparent;
                            .card-img{
                                width: 100%;
                                height: 100%; 
                            }
                            .card-body{
                                &:hover{
                                width: 100%;
                                height: 100%;    
                                background-image: none;
                                background-color: black;    
                                color: white;
                                }
                                
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
        }
</style>