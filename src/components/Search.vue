<template>


    <header>
        <nav>
            <div class="container-lg">
                <div class="row d-flex py-3">
                    <div class="col-2">
                        <img src="/img/Netflix-logo.png" alt="">
                    </div>

                    <div class="col-6 py-2">
                        <ul>
                            <li><a href="#">Home</a></li>
                            <li><a href="#">Serie Tv</a></li>
                            <li><a href="#">Film</a></li>
                            <li><a href="#">Nuovi e Popolari</a></li>
                            <li><a href="#">La mia lista</a></li>
                        </ul>
                    </div>

                    <div class="col-4 d-inline-flex">

                    <input type="text" 
                        class="form-control" 
                        placeholder="Scegli un titolo"
                        v-model.trim="inputText"
                    >

                    <button type="submit" 
                    class="ms-2 px-2"
                    @click.prevent="$emit('search',inputText)"
                    >Cerca</button>               

                    </div>

                </div>

            </div>

        </nav>
    </header>
     
</template>

<script>
export default {
    name: "Search",
    data(){
        return {
            inputText:'',
        }
    } 
}
</script>

<style scoped lang="scss">

    header{
        background-color: black;
        // height: 70px;
        height: 7vh;
            nav{
                .container-lg{
                    .row{
                        .col-2{
                            img{
                                height: 50px;
                                width: 100px;
                                vertical-align: middle;
                                // padding: 20px 0;
                            }
                        }
                        .col-6{

                            ul{

                                li{
                                    display: inline-block;
                                    list-style: none;

                                    a{
                                        text-decoration: none;
                                        color: white;
                                        padding: 0 10px;
                                    }
                                }
                            }
                        }
                        
                    }
                }
            }
        }

</style>