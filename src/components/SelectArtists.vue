<template>
  <div class="mb-5 d-flex flex-column">
    <label class="text-white">Filtra per artista</label>
    <select class="px-3 py-2" v-model="selected" @change="$emit('selectAuthor', selected)">
      <option value="">All</option>
      <option v-for="(author, index) in authorsList" :key="index" :value="author">{{author}}</option>
    </select>
  </div>
</template>

<script>
export default {
  name: 'SelectArtists',
  props:{
    authorsList: {
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
