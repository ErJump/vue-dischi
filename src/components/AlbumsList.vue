<template>
  <div class="row">
    <AlbumCard/>
  </div>
</template>

<script>
import AlbumCard from './AlbumCard.vue';
export default {
  name: 'AlbumsList',
  components: {
    AlbumCard,
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
@import "../assets/styles/variables.scss";
  
</style>
