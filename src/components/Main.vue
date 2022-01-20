<template>
  <main>
    <Card v-for="(card, index) in cards" :key="index" :info="card" />
  </main>
</template>

<script>
import Card from "./Card.vue";

export default {
    name: 'Main',
    components: {
      Card,
    },
    props: {
      cards: {
        type: Array,
        default() {
          return [];
        },
      },
    },
    data(){
        return{
            
        }
    },
}
</script>

<style>

</style>