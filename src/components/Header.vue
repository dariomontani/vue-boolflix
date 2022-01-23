<template>
    <div class="row">
        <div class="d-flex justify-content-around">
            <div>
                <a href="https://fontmeme.com/netflix-font/"><img src="https://fontmeme.com/permalink/220121/0a43aa36584f2895324a0006b42b5d1a.png" alt="netflix-font" border="0"></a>
            </div>
            <div class="mt-4">
                <form class="d-flex">

                    <input v-model="textSearch" class="form-control me-2" type="text" placeholder="Search" aria-label="Search">

                    <button @click="$emit('searchFilm', textSearch)" class="btn btn-outline-danger" type="button">Search</button>
                    
                </form>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'Header',
    data(){
        return{
            textSearch:"",
        }
    }
}
</script>

<style lang='scss'>

</style>