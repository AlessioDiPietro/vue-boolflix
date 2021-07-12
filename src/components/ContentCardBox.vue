<template>

  <section class="card_box d-flex flex-wrap">
    <div v-for="items in itemsList" :key="items.id" class="col-3">
    <ContentCard/>
    </div>
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
          this.itemsList = response.data.results
          console.log(this.itemsList);
        })
      }
    }
    

}
</script>

<style>

</style>