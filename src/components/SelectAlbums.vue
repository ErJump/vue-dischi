<template>
  <div class="mb-5">
    <select class="px-3 py-2" v-model="selected" @change="$emit('select', selected)">
      <option value="">All</option>
      <option value="Rock">Rock</option>
      <option value="Metal">Metal</option>
      <option value="Pop">Pop</option>
      <option value="Jazz">Jazz</option>
    </select>
  </div>
</template>

<script>
export default {
  name: 'SelectAlbums',
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
