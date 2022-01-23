<template>
  <div class="card">
      <ul>
        <div class="cover">
            <img :src="`https://image.tmdb.org/t/p/original${info.poster_path}`" alt="">
        </div>
        <li>
            <h4>TITOLO</h4>
            <p>{{ (info.title) ? info.title : info.name }}</p>
        </li>
        <li>
            <h4>TITOLO ORIGINALE</h4>
            <p>{{ (info.original_title) ? info.original_title : info.original_name }}</p>
        </li>
        <li>
            <h4>LINGUA</h4>
            <p><i :class="'flag flag-' + addFlag(info.original_language)"></i></p>
        </li>
        <li>
            <h4>VOTO</h4>
            <p>{{info.vote_average}}</p>
        </li>
      </ul>
  </div>
</template>

<script>

export default {
    name: 'Card',
    props: {
        info: Object,
    },
    methods: {
        addFlag(language) {
            if (language == "en") {
                return "us";
            }
            return language;
        },
    },
}
</script>

<style lang="scss">
    @import '~mdb-ui-kit/css/mdb.min.css';
    .card{
        width: 300px;
        margin: 1em;
        border: 1px solid black;
        ul{
            list-style: none;
            .cover{
                img{
                    width: 100%;
                    max-height: 400px;
                }
            }
        }
    }
</style>

// Milestone 3:
// Trasformiamo poi il voto da 1 a 10 decimale in un numero intero da 1 a 5, così da permetterci di stampare a schermo un numero di stelle piene che vanno da 1 a 5, lasciando le restanti vuote (troviamo le icone in FontAwesome).
// Arrotondiamo sempre per eccesso all’unità successiva

