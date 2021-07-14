<template>
  <div class="card-box  position-relative">
      <img :src="info.poster_path == null ? 'https://cdn.browshot.com/static/images/not-found.png' : 'https://image.tmdb.org/t/p/w500/'+info.poster_path">
      <div class="info_text position-absolute">

        <ul>
          <li><h3><strong>Titolo:</strong>{{info.title == null? info.name : info.title}}</h3></li>
          <li><h5><strong>Titolo originale:</strong>{{info.original_title == null? info.original_name : info.original_title}}</h5></li>
          <li>
            <h6><strong>Lingua:</strong></h6>
      <img :src="info.original_language == 'en' ? 'https://www.countryflags.io/gb/shiny/64.png':'https://www.countryflags.io/'+ info.original_language +'/shiny/64.png'">
          </li>
          <li>
            <h5><strong>Voto:</strong>{{info.vote_average}}</h5>
            
          </li>
        </ul>

      </div>  
  </div>
</template>

<script>
export default {
  name:"GlobalContentCard",
  props:["info"],
  data(){
    return {
      
      flagData: "en"
    }
  }
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