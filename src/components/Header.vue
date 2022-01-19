<template>

<div class="row">
    <div class="col-4">
        <form class="d-flex">
            <input v-model="inputText" class="form-control me-2" type="text" placeholder="Search" aria-label="Search">
            <button @click="$emit('searchFilm', inputText)" class="btn btn-outline-success" type="button">Search</button>
        </form>
    </div>
</div>

</template>

<script>
export default {
    name: 'Header',
    data(){
        return{
            inputText:"",
        }
    }
}
</script>

<style lang='scss'>
    
</style>