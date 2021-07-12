<template>
  <div class="container">

      <!-- searchbar -->
      <div class="box text-end my-5">
          <input type="text" placeholder="Inserisci parola chiave..">
          <button type="submit">Ricerca</button>
      </div>

      <!-- area risultati -->
      <div class="res_area">
          
          <ContentCardBox/>
          
      </div>
  </div>
</template>

<script>
import ContentCardBox from '@/components/ContentCardBox.vue'
export default {
    name: "Content",
    components: {
        ContentCardBox
    },
    
}
</script>

<style lang="scss" scoped>
    .res_area {
        background-color: grey;
        min-height: 300px;
    }
</style>