<template>
  <div class="mb-5 d-flex flex-column">
    <label class="text-white">Filtra per genere</label>
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
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
</style>
