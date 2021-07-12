<template>

    <div class="box text-end my-5">
          <input type="text" placeholder="Inserisci parola chiave.." v-model="searchText">

          <button type="submit" @click.prevent="$emit('inputSearch',searchText)">Ricerca</button>

          <button type="reset">Annulla</button>
      </div>
  
</template>

<script>
export default {
    name: 'SearchBar',
    data(){
        return {
            searchText: ""
        }
    }

}
</script>

<style>

</style>