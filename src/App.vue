<template>
  <div id="app">


    <header>
      <!-- icona/logo -->
      <HeadSearch @textSearch = "resultSearch"/>
    </header>

    <!-- corpo pagina -->
    <main>
      <Content :contentList="itemsMovieList"/>
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
      apiUrl: "https://api.themoviedb.org/3/search/movie",
      apiKey: "3c2a6196907d164353ad9b7c59139463",
      language: "it-IT",
      itemsMovieList : []
      
    }
  },
  methods: {
    resultSearch(text){
      axios
      .get(this.apiUrl, {
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
      this.dataSearchText = text
    }
  }
}
</script>

<style lang="scss">
@import "@/style/Commons.scss";

</style>
