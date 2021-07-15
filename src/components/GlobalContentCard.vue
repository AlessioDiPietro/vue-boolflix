<template>
  <div class="card_box position-relative m-5">

      <img class="container-fluid poster" :src="info.poster_path == null ? 'https://cdn.browshot.com/static/images/not-found.png' : 'https://image.tmdb.org/t/p/w342/'+info.poster_path">


      <div class="info_text position-absolute">
        <ul>
          <li>
            <h3>{{info.title == null? info.name : info.title}}</h3>
          </li>
          <li>
            <h5>"{{info.original_title == null? info.original_name : info.original_title}}"</h5>
          </li>
          <li>
            <h6>Lingua: </h6>
            <img :src="info.original_language == 'en' ? 'https://www.countryflags.io/gb/shiny/24.png':'https://www.countryflags.io/'+ info.original_language +'/shiny/24.png'">
          </li>

          <li class="position-relative">
            <h6>Voto: </h6>
            <div class="static_star">
              <i class="fas fa-star" v-for="(itemsC, indexC) in 5" :key="indexC"></i>
            </div>

            <div class="rated_star position-absolute bottom-0">
              <i class="fas fa-star text-warning" v-for="(itemsC, indexC) in voteData" :key="indexC"></i>
            </div>
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
      voteData: Math.ceil(this.info.vote_average)*0.5,
      
    }
  }

}
</script>

<style lang="scss" scoped>
.card_box {
  background-color: black;
  .poster{
    height: 452px;
  }
  .info_text {
    display: none;
  }
  &:hover {
    .poster {
      opacity: 0.2;
    }
    .info_text {
      z-index: 999;
      top:0;
      color: white;
      display: block;
      ul{
        padding: 0.5rem;
        li{
          list-style: none;
          margin-bottom: 18px;
          h3 {
            color: #eb8787;
            font-size: 40px !important ;
          }
          h5 {
            font-size: 15px;
          }
          h6 {
            display: inline;
            font-size: 18px;
          }
          img {
            display: inline
          }
        }
      }
    }
  }
  
    
}
</style>