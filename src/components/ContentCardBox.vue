<template>

  <section>
      <h1>Ultime Uscite</h1>
      <div class="grey_opacity p-2 rounded">
        <SearchBar @inputSearch="filterBySearch"/>
        <div class="card_box d-flex" v-if="!loadingPage">
          <div v-for="items in filtredItems" :key="items.id" class="col">
            <ContentCard :info="items" class="m-3"/>
          </div>
        </div>

        <!-- caricamento alternativa -->
        <div v-else class="load d-flex justify-content-center align-items-center">
          <h2>La Pirateria è REATO!</h2>
        </div> 
      </div>     
  </section>

</template>

<script>
import ContentCard from '@/components/ContentCard.vue'
import SearchBar from '@/components/SearchBar.vue'
import axios from 'axios'
export default {
  name: 'ContentCardBox',
  components: {
    ContentCard,
    SearchBar
  },
  data(){
    return{
      apiUrlDesc: "https://api.themoviedb.org/3/discover/movie?api_key=3c2a6196907d164353ad9b7c59139463&language=it-IT&sort_by=popularity.desc&include_adult=false&include_video=false&page=1&with_watch_monetization_types=flatrate",
      loadingPage: true,
      itemsList: [],
      filterInput: ""
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

      })
    },
    filterBySearch(searchText){
      this.filterInput = searchText
    }
  },
  computed: {
    filtredItems(){
      return this.itemsList.filter(element => {
        return element.title.toLowerCase().includes(this.filterInput.toLowerCase())
      })
    }
    
  }
    
}

</script>

<style lang="scss" scoped>
.grey_opacity {
  background-color: #0000001c;
  h1 {
  font-size: 40px;
  font-weight: bolder;
  text-shadow: 1px 1px #FF0000;
  margin-bottom: 2rem;
  }
  .card_box {
    overflow-x: scroll;
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
}


</style>