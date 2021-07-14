<template>
  <section class="box_film">
      <div class="box_film my-3 d-flex">
          <h2>Risultati Film:</h2>
          <div class="row">

          <GlobalContentCard :info="items" v-for="(items, index) in films" :key="index" class="col-3"/>
          </div>
          
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
    border-bottom: 3px solid rgb(110, 6, 6);
    display: inline-block;
}

</style>