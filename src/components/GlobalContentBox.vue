<template>
  <section>
      <div class="box_film">
          <h2>Risultati Film:</h2>
          <GlobalContentCard :info="items" v-for="(items, index) in films" :key="index"/>
      </div>
      <div class="box_series">
          <h2>Risultati Series:</h2>
          <GlobalContentCardSeries :infoSeries="items" v-for="(items, index) in series" :key="index"/>
      </div>
  </section>
</template>

<script>
// import axios from "axios"
import GlobalContentCard from "@/components/GlobalContentCard.vue"
import GlobalContentCardSeries from "@/components/GlobalContentCardSeries.vue"
export default {
    name:"GlobalContentBox",
    props:["films","series"],
    components: {
        GlobalContentCardSeries,
        GlobalContentCard
    },
    
            

}
</script>

<style lang="scss" scoped>
.box-film {
    background-color: green;
    }
.box-series {
    background-color: purple;
    }

</style>