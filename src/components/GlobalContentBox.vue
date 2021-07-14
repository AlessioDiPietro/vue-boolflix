<template>
  <section>
      <div class="box_film my-3">
          <h2>Risultati Film:</h2>
          <GlobalContentCard :info="items" v-for="(items, index) in films" :key="index"/>
          
      </div>
      <div class="box_series my-3">
          <h2>Risultati Series:</h2>
          <GlobalContentCard :info="items" v-for="(items, index) in series" :key="index"/>
      </div>
  </section>
</template>

<script>
import GlobalContentCard from "@/components/GlobalContentCard.vue"
export default {
    name:"GlobalContentBox",
    props:["films","series"],
    components: {
        GlobalContentCard
    },
    
            

}
</script>

<style lang="scss" scoped>
h2 {
    font-size: 40px;
    font-weight: bolder;
    text-shadow: 1px 1px #FF0000;
    margin-bottom: 2rem;
}
.box-film {
    background-color: green;
    }
.box-series {
    background-color: purple;
    }

</style>