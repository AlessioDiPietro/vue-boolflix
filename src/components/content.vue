<template>
  <div class="container-fluid bg-dark content_container -text-light">

    <!-- ricerca ultimi usciti -->
    <div class="res_area_last">
          
        <ContentCardBox/>
          
    </div>
    <!-- ricerca globale -->
    <div class="res_area_all">

      <GlobalContentBox :films="contentList" :series="contentSeriesList"/>

    </div>

    
  </div>
</template>

<script>
import ContentCardBox from '@/components/ContentCardBox.vue'
import GlobalContentBox from '@/components/GlobalContentBox.vue'
export default {
    name: "Content",
    props: ["contentList", "contentSeriesList"],
    components: {
        ContentCardBox,
        GlobalContentBox
    },
    
}
</script>

<style lang="scss">
.content_container {
  min-height: calc(100vh - 100px);
}
</style>