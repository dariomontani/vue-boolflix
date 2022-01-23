<template>
  <main>
    <div class="containerCards" v-if="cards.length > 0">
      <Card v-for="(card, index) in cards" :key="index" :info="card" />
    </div>
    <div class="noRisultato" v-else>
      <h2>Nessun Risultato</h2>
    </div>
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

<style lang="scss">
  .containerCards{
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
  }
  .noRisultato{
    height: 100vh;
    color: white;
    display: flex;
    justify-content: center;
    align-items: center;
  }
</style>