<template>
  <div class="row">
    <AlbumCard/>
  </div>
</template>

<script>
import AlbumCard from './AlbumCard.vue';
import axios from 'axios';
export default {
  name: 'AlbumsList',
  components: {
    AlbumCard,
  },
  data() {
    return {
      albums: [],
    };
  },
  methods: {
    getAlbums() {
      axios.get('https://flynn.boolean.careers/exercises/api/array/music')
        .then(response => {
          this.albums = response.data.response;
          console.log(this.albums);
        })
        .catch(error => {
          console.warn(error);
        });
    },
  },
  created() {
    this.getAlbums();
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
@import "../assets/styles/variables.scss";
  
</style>
