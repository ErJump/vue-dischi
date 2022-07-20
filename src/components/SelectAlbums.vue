<template>
  <div class="mb-5">
    <select class="px-3 py-2" v-model="selected" @change="$emit('select', selected)">
      <option value="">All</option>
      <option v-for="(genre, index) in genresList" :key="index" :value="genre">{{genre}}</option>
    </select>
  </div>
</template>

<script>
export default {
  name: 'SelectAlbums',
  props:{
    genresList: {
      type: Array,
      required: true,
    },
  },
  data: function () {
    return {
      selected: '',
    }
  },
  methods: {
    log: function (string){
      console.log(string);
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
</style>
