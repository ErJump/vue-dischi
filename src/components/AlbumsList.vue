<template>
  <div>
    <SelectAlbums @select="setSelected" :genresList="genres"/>
    <div v-if="!loading" class="row">
      <AlbumCard v-for="album in filterInAlbumsforGenres" :key="album.id"
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
      selected: "",
      filteredAlbums: [],
      genres: [],
    };
  },
  methods: {
    getAlbums() {
      axios.get('https://flynn.boolean.careers/exercises/api/array/music')
        .then(response => {
          this.albums = response.data.response;
          this.pushGenres();
          this.loading = false;
        })
        .catch(error => {
          console.warn(error);
        });
    },
    setSelected(selected) {
      this.selected = selected;
    },
    pushGenres() {
      this.albums.forEach(album => {
        if (!this.genres.includes(album.genre)) {
          this.genres.push(album.genre);
        }
      });
    },
  },
  created() {
    this.getAlbums();
  },
  computed: {
    filterInAlbumsforGenres() {
      return this.albums.filter(album => album.genre.includes(this.selected));
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
@import "../assets/styles/variables.scss";
  
</style>
