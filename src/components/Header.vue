<template>
    <header>
        <nav>
            <div class="container-lg">
                <div class="row">
                    <div class="col-2">
                        <img src="@/img/Netflix-logo.png" alt="">
                    </div>

                    <div class="col-5">
                        
                    </div>
                </div>
            </div>

        </nav>
    </header>
</template>

<script>
export default {
    name: "Header",
}
</script>

<style scoped lang="scss">
    header{
        background-color: black;
        // height: 70px;
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
                        
                    }
                }
            }
    }
</style>