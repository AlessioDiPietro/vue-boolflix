<template>
  <div class="position-relative">
      <img :src="info.poster_path == null ? 'https://cdn.browshot.com/static/images/not-found.png' : 'https://image.tmdb.org/t/p/w185/'+info.poster_path">
      <div class="info_text position-absolute">
        <ul>
          <li><h2>{{info.title}}</h2></li>
          <li>{{info.original_title}}</li>
          <li>IMB: {{info.vote_average}}</li>
        </ul>

        

        <div></div>

        

        <div></div>
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

<style lang="scss">
.info_text {
  z-index: 999;
  bottom:0;
  color: white;

}

</style>