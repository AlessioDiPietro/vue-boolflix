<template>
  <div class="card">
      <img src="" alt="">
      <h3><strong>Titolo:</strong>{{info.title}}</h3>
      <h5><strong>Titolo originale:</strong>{{info.original_title}}</h5>
      <h5><strong>Lingua:</strong>{{info.original_language}}</h5>
      <h5><strong>Voto:</strong>{{info.vote_average}}</h5>
      
      
  </div>
</template>

<script>
export default {
  name:"GlobalContentCard",
  props:["info"]

}
</script>

<style>

</style>