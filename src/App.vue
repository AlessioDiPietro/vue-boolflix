<template>
  <div id="app">


    <header>
      <!-- icona/logo -->
      <HeadSearch @textSearch = "resultSearch"/>
    </header>

    <!-- corpo pagina -->
    <main>
      <Content :contentList="itemsMovieList" :contentSeriesList="itemsSeriesList" :textSearch="dataSearchText"/>
    </main>


  <footer>
    <!-- pie di pagina -->
  </footer>


  </div>
</template>

<script>

import Content from "@/components/Content.vue"
import HeadSearch from "@/components/HeadSearch.vue"
import axios from 'axios'
// import axios from "axios"

export default {
  name: 'App',
  components: {
    Content,
    HeadSearch
  },
  data(){
    return {
      dataSearchText: "",
      apiUrlMovie: "https://api.themoviedb.org/3/search/movie",
      apiUrlSeries: "https://api.themoviedb.org/3/search/tv",
      apiKey: "3c2a6196907d164353ad9b7c59139463",
      language: "it-IT",
      itemsMovieList : [],
      itemsSeriesList : []
      
    }
  },
  methods: {
    resultSearch(text){
      this.dataSearchText = text;

      axios
      .get(this.apiUrlMovie, {
        params: {
          api_key: this.apiKey,
          language: this.language,
          query: text
        }
      })
      .then(response =>{
        this.itemsMovieList = response.data.results
        console.log(this.itemsMovieList)
      })

      axios
      .get(this.apiUrlSeries,{
        params:{
          api_key: this.apiKey,
          language: this.language,
          query: text
        }
      
      })
      .then(response =>{
        this.itemsSeriesList = response.data.results
      })
    }
  }
}
</script>

<style lang="scss">
@import "@/style/Commons.scss";

</style>
