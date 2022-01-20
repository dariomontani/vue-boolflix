<template>
  <div class="card">
      <ul>
          <li>{{info.title}}</li>
          <li>{{info.original_title}}</li>
          <li>{{info.original_language}}</li>
          <li>{{info.vote_average}}</li>
      </ul>
  </div>
</template>

<script>
export default {
    name: 'Card',
    props: {
        info: Object,
    }
}
</script>

<style>

</style>