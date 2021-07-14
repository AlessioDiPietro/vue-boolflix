<template>

    <div class="box m-2 text-end bg-transparent">
          <input class="border-0 rounded-pill py-1 px-2 grey" type="text" placeholder="Ricerca tra le ultime uscite.." @keyup.enter="$emit('inputSearch',searchText)" v-model.trim="searchText">

          <button class="btn btn-light mx-2" type="submit" @click.prevent="$emit('inputSearch',searchText)">Ricerca</button>

          <button type="reset" class="btn btn-danger" @click.prevent="resetAll">Annulla</button>
      </div>
  
</template>

<script>
export default {
    name: 'SearchBar',
    data(){
        return {
            searchText: ""
        }
    },
    methods: {
        resetAll(){
            this.searchText = "";
            this.$emit('inputSearch', this.searchText)
        }
    }

}
</script>

<style lang="scss" scoped>
.grey {
    color: gray;
}

</style>