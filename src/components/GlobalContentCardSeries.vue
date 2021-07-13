<template>
  <div class="card">
      
      <img src="" alt="">
      <h3><strong>Titolo:</strong>{{infoSeries.name}}</h3>
      <h5><strong>Titolo originale:</strong>{{infoSeries.original_title}}</h5>
      <h5><strong>Lingua:</strong>{{infoSeries.original_language}}</h5>
      <img :src="'https://www.countryflags.io/'+ infoSeries.origin_country +'/shiny/64.png'">
      <h5><strong>Voto:</strong>{{infoSeries.vote_average}}</h5>
      
      
  </div>
</template>

<script>
export default {
    name: "GlobalContentCardSeries",
    props:["infoSeries"]

}
</script>

<style>

</style>