<template>
  <div>
      <img src="" alt="">

      <h2>{{info.title}}</h2>

      <div>{{info.original_title}}</div>

      <div>{{info.original_language}}</div>

      <div>{{info.vote_average}}</div>

      <!-- info -->
  </div>
</template>

<script>
export default {
    name: "contentCard",
    props: ["info"]

}
</script>

<style>

</style>