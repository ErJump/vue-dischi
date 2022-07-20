<template>
  <div>
    <div class="d-flex">
      <SelectAlbums class="px-4" @select="setSelected" :genresList="genres"/>
      <SelectArtists :authorsList="authors"/>
    </div>
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
import SelectArtists from './SelectArtists.vue';
export default {
  name: 'AlbumsList',
  components: {
    AlbumCard,
    AlbumLoader,
    SelectAlbums,
    SelectArtists,
},
  data() {
    return {
      albums: [],
      loading: true,
      selected: "",
      filteredAlbums: [],
      genres: [],
      authors: [],
    };
  },
  methods: {
    getAlbums() {
      axios.get('https://flynn.boolean.careers/exercises/api/array/music')
        .then(response => {
          this.albums = response.data.response;
          this.pushGenres();
          this.pushAuthors();
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
    pushAuthors() {
      this.albums.forEach(album => {
        if (!this.authors.includes(album.author)) {
          this.authors.push(album.author);
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
