<template>
  <div class="card-box position-relative">
      
      <img :src="infoSeries.poster_path == null ? 'https://cdn.browshot.com/static/images/not-found.png' : 'https://image.tmdb.org/t/p/w500/'+infoSeries.poster_path">>
      <div class="info_text position-absolute">
          <ul>
                <li><h3><strong>Titolo:</strong>{{infoSeries.name}}</h3></li>
                <li><h5><strong>Titolo originale:</strong>{{infoSeries.original_title}}</h5></li>
                <li>
                  <h6><strong>Lingua:</strong></h6>
                  <img :src="infoSeries.original_language == 'en' ? 'https://www.countryflags.io/bg/shiny/64.png':'https://www.countryflags.io/'+ infoSeries.original_language +'/shiny/64.png'">
                </li>
                <li>
                  <h5><strong>Voto:</strong>{{infoSeries.vote_average}}</h5>
                  
                </li>
              
          </ul>
      
      
      
      
      

      </div>
      
      
  </div>
</template>

<script>
export default {
    name: "GlobalContentCardSeries",
    props:["infoSeries"]

}
</script>

<style lang="scss" scoped>
.info_text {
    z-index: 999;
    bottom:0; 
    color: white;
    h6{
        display: inline;
    }
    img {
        display: inline
    }
}
    


</style>