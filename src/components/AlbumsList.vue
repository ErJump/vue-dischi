<template>
  <div>
    <SelectAlbums/>
    <div v-if="!loading" class="row">
      <AlbumCard v-for="album in albums" :key="album.id"
      :object="album"/>
    </div>
    <div v-else>
      <AlbumLoader/>
    </div>
  </div>
</template>

<script>
import AlbumCard from './AlbumCard.vue';
import AlbumLoader from './AlbumLoader.vue';
import axios from 'axios';
import SelectAlbums from './SelectAlbums.vue';
export default {
  name: 'AlbumsList',
  components: {
    AlbumCard,
    AlbumLoader,
    SelectAlbums
},
  data() {
    return {
      albums: [],
      loading: true,
    };
  },
  methods: {
    getAlbums() {
      axios.get('https://flynn.boolean.careers/exercises/api/array/music')
        .then(response => {
          this.albums = response.data.response;
          console.log(this.albums);
          this.loading = false;
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
