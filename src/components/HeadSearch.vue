<template>
  <div>
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

<style>

</style>