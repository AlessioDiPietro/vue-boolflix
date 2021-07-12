<template>

    <div class="box text-end my-5">
          <input type="text" placeholder="Inserisci parola chiave.." @keyup.enter="$emit('inputSearch',searchText)" v-model.trim="searchText">

          <button type="submit" @click.prevent="$emit('inputSearch',searchText)">Ricerca</button>

          <button type="reset" @click.prevent="resetAll">Annulla</button>
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

<style>

</style>