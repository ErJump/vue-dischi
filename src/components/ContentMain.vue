<template>
  <div class="my_main">
    <div class="container-lg py-5">
      <AlbumsList/>
    </div>
  </div>
</template>

<script>
import AlbumsList from './AlbumsList.vue';
export default {
  name: 'ContentMain',
  components: {
    AlbumsList,
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
@import "../assets/styles/variables.scss";
  .my_main {
    background-color: $mainBG;
    height: calc(100vh - 70px);
  }
</style>
