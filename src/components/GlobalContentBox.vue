<template>
  <section>
      <div class="box">
          <GlobalContentCard :info="items" v-for="(items, index) in films" :key="index"/>
      </div>
  </section>
</template>

<script>
// import axios from "axios"
import GlobalContentCard from "@/components/GlobalContentCard.vue"
export default {
    name:"GlobalContentBox",
    props:["films"],
    components: {
        GlobalContentCard,
    },
    
            

}
</script>

<style>

</style>