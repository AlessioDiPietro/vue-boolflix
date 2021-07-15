<template>
  <section>
    <div class="box_content" v-if="!searchTxt ==''">
        <h2>Risultati Film:</h2>
        <div class="d-flex border-bottom">
            <div class="row">

                <GlobalContentCard :info="items" v-for="(items, index) in films" :key="index" class="col-2"/>

            </div>
                
        </div>

        <h2>Risultati Series:</h2>
        <div class="d-flex">
            <div class="row">

                <GlobalContentCard :info="items" v-for="(items, index) in series" :key="index" class="col-2"/>

            </div>
        </div>
    </div>
    <!-- oppure -->
    <div v-else class="alternative py-5">
        <h2>Inizia qui la tua ricerca..</h2>
    </div>
    
        


  </section>
</template>

<script>
import GlobalContentCard from "@/components/GlobalContentCard.vue"
export default {
    name:"GlobalContentBox",
    props:["films","series","searchTxt"],
    components: {
        GlobalContentCard
    },
    
            

}
</script>

<style lang="scss" scoped>
.box_content{
    .row {
        --bs-gutter-x: 0;
    }
    h2 {
        font-size: 40px;
        font-weight: bolder;
        text-shadow: 1px 1px #FF0000;
        margin-bottom: 2rem;
        border-bottom: 3px solid rgb(110, 6, 6);
        display: inline-block;
    }

}
.alternative {
    text-align: center;
    h2{
        font-size: 50px;
        color: grey;  
        opacity: 0.2;
    }  
}
</style>