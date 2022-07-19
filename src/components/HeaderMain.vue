<template>
  <div class="my_header container-fluid py-2 px-4 d-flex justify-content-between">
    <img src="https://www.freepnglogos.com/uploads/spotify-logo-png/spotify-icon-marilyn-scott-0.png" alt="spotify logo">
  </div>
</template>

<script>
export default {
  name: 'HeaderMain',
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
@import "../assets/styles/variables.scss";
  .my_header {
    background-color: $headerBG;
    height: 70px;
  }
</style>
