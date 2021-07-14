<template>
  <div class="head d-flex justify-content-between align-items-center p-4">
      <img src="https://image.flaticon.com/icons/png/512/249/249117.png" alt="boolfix">
      <SearchBar @inputSearch="resSearchText" />
  </div>
</template>

<script>
import SearchBar from './SearchBar.vue'
export default {
    name: "HeadSearch",
  components: { 
    SearchBar, 
    },
  data(){
    return {
      textSearchIn: ""
    }
  },
  methods: {
    resSearchText(searchText){
      this.textSearchIn = searchText;
      this.$emit('textSearch', searchText);
      
    }
  }
}
</script>

<style lang="scss">
.head {
  height: 100px;
  background-color: #1c1c1c;
  img {
    height: 100%;
  }
}

</style>