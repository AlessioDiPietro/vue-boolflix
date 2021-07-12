<template>

  <section class="card_box d-flex flex-wrap" v-if="!loadingPage">
    <div v-for="items in itemsList" :key="items.id" class="col-3">
    <ContentCard :info="items"/>
    </div>
    
  </section>

  <!-- caricamento alternativa -->
  <section v-else class="load d-flex justify-content-center align-items-center">
    <h2>La Pirateria è REATO!</h2>
  </section>
  
</template>

<script>
import ContentCard from '@/components/ContentCard.vue'
import axios from 'axios'
export default {
  name: 'ContentCardBox',
  components: {
    ContentCard,
  },
  data(){
    return{
      apiUrlDesc: "https://api.themoviedb.org/3/discover/movie?api_key=3c2a6196907d164353ad9b7c59139463&language=it-IT&sort_by=popularity.desc&include_adult=false&include_video=false&page=1&with_watch_monetization_types=flatrate",
      loadingPage: true,
      itemsList: []
    }
  },
  created(){
    this.getItemList();
  },
  methods: {
    getItemList(){
      axios
        .get(this.apiUrlDesc)
        .then(response =>{
          this.itemsList = response.data.results;
          this.loadingPage = false;
          console.log(this.itemsList);
        })
      }
    }
    

}
</script>

<style lang="scss" scoped>
.card_box {
  background-color: blanchedalmond;
  min-height: 300px;
}
.load {
  background: rgb(4,8,8);
  background: linear-gradient(7deg, rgba(4,8,8,1) 0%, rgba(80,71,71,1) 54%, rgba(180,12,10,1) 100%);
  height: 70vh;
  H2 {
    color: chartreuse;
    font-weight: bolder;
    font-size: 40px;
    font-style: oblique;
    text-decoration: underline;
  }
}

</style>