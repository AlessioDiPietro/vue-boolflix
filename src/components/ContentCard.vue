<template>
  <div class="position-relative box_last">
      <img :src="info.poster_path == null ? 'https://cdn.browshot.com/static/images/not-found.png' : 'https://image.tmdb.org/t/p/w185/'+info.poster_path">
      <div class="info_text position-absolute">
        <ul>
          <li><h2>{{info.title}}</h2></li>
          <li>{{info.original_title}}</li>
          <li>IMB: {{info.vote_average}}</li>
        </ul>
      </div>

      <!-- info -->
  </div>
</template>

<script>
export default {
    name: "contentCard",
    props: ["info"]

}
</script>

<style lang="scss" >
.box{
  background-color: black;
  &:hover {
    img{
      opacity: 0.2;
    }
    .info_text {
      display: block;
    }
  }
  img {
    height: 278px
  }
  .info_text {
    z-index: 999;
    top:0;
    color: white;
    font-size: 15px;
    display: none;
    ul{
      padding: 0.5rem;
      li{
        list-style: none;
        h2{
          margin: 1rem 0;
          font-size: 25px;
        }
      }
    }
  
  }
}

</style>