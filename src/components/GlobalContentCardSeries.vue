<template>
  <div class="card">
      <img src="" alt="">
      <h3><strong>Titolo:</strong>{{infoSeries.name}}</h3>
      <h5><strong>Titolo originale:</strong>{{infoSeries.original_title}}</h5>
      <h5><strong>Lingua:</strong>{{infoSeries.original_language}}</h5>
      <img :src="flag ==='en'? enFlag : itFlag" alt="">
      <h5><strong>Voto:</strong>{{infoSeries.vote_average}}</h5>
      
      
  </div>
</template>

<script>
export default {
    name: "GlobalContentCardSeries",
    props:["infoSeries"],
    data(){
        return{
            flag: "",
            enFlag: "https://image.flaticon.com/icons/png/512/197/197374.png",
            itFlag:"https://as1.ftcdn.net/jpg/01/77/89/96/500_F_177899610_lBWg6Wbvwla4ypmmk0PZNwcadHozvb3X.jpg"
        }
    },
    created:{
        changeFlag(){
            if (this.infoSeries.original_language == "en"){
                this.flag = this.enFlag;
            }
        }
    }

}
</script>

<style>

</style>