<template>
  <div class="card">
      {{info.title}}
      {{info.original_title}}
      {{info.oroginal_language}}
      {{info.language}}
      {{info.vote_average}}
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