<template>
  <div id="app">


    <header>
      <!-- icona/logo -->
    </header>

    <!-- corpo pagina -->
    <main>
      <Content/>
    </main>


  <footer>
    <!-- pie di pagina -->
  </footer>


  </div>
</template>

<script>

import Content from "@/components/Content.vue"

export default {
  name: 'App',
  components: {
    Content,
  }
}
</script>

<style lang="scss">
@import "@/style/Commons.scss";

</style>
