<template>
  <div id="app">
    <HeaderMain/>
    <ContentMain/>
  </div>
</template>

<script>
import ContentMain from './components/ContentMain.vue';
import HeaderMain from './components/HeaderMain.vue';

export default {
  name: 'App',
  components: {
    ContentMain,
    HeaderMain
  }
}
</script>

<style lang="scss">
@import "assets/styles/variables.scss";
@import "~bootstrap/dist/css/bootstrap.css";
</style>
