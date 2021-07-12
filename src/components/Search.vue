<template>
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

<style>

</style>