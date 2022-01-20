<template>
  <div class="card">
      <ul>
        <li>
            <h4>TITOLO</h4>
            <p>{{info.title}}</p>
        </li>
        <li>
            <h4>TITOLO ORIGINALE</h4>
            <p>{{info.original_title}}</p>
        </li>
        <li>
            <h4>LINGUA</h4>
            <p><i :class="'flag flag-' + (info.original_language)"></i></p>
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
}
</script>

<style>
    @import '~mdb-ui-kit/css/mdb.min.css';
    .card{
        border: 1px solid black;
    }
</style>
