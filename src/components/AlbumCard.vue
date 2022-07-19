<template>
  <div class="col-2 my_card p-3 d-flex flex-column align-items-center mx-3 mb-4">
    <img class="img-fluid mb-3" :src="object.poster" :alt="object.poster">
    <h3 class="text-white text-uppercase mb-2 fs-5 text-center">{{object.title}}</h3>
    <span>{{object.author}}</span>
    <span>{{object.year}}</span>
  </div>
</template>

<script>
export default {
  name: 'AlbumCard',
  props: {
    object: {
      type: Object,
      required: true,
    },
  },
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
