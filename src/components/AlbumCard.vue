<template>
  <div class="col-2 my_card p-3 d-flex flex-column align-items-center mx-3 mb-4">
    <img class="img-fluid mb-3" src="https://cdn2.jazztimes.com/2018/05/SteveGadd-800x723.jpg" alt="">
    <h3 class="text-white text-uppercase mb-2">Titolo</h3>
    <span>Artista</span>
    <span>Anno</span>
  </div>
</template>

<script>
export default {
  name: 'AlbumCard',
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
@import "../assets/styles/variables.scss";
  .my_card {
    background-color: $headerBG;
    height: 400px;
    span{
      color: $subColor;
    }
  }

</style>
