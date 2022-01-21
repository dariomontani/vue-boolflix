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
        border: 1px solid black;
        ul{
            .cover{
                width: 100px;
                height: 150px;
                img{
                    width: 100%;
                }
            }
        }
    }
</style>
