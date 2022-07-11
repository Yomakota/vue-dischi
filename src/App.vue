<template>
  <div id="app">
    <HeaderPage @changeGenre="setGenre($event)" :genres="genresList" />
    <MainPage :genre="selectValue" @genresStart="setGenresList($event)" />
  </div>
</template>

<script>
import HeaderPage from "./components/HeaderPage.vue";
import MainPage from "./components/ListAlbums.vue";

export default {
  name: 'App',
  components: {
    HeaderPage,
    MainPage,
  },
  data() {
    return {
      selectValue: '',
      genresList: [],
    }
  },
  methods: {
    setGenre(value) {
      this.selectValue = value;
    },
    setGenresList(value) {
      this.genresList = value;
    },
  }
}
</script>

<style lang="scss">
@import "./assets/scss/style.scss";
</style>
