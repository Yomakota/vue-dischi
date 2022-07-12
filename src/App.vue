<template>
  <div id="app">
    <HeaderPage @changeGenre="setGenre" :genres="genresList" @changeAuthor="setAuthor" :authors="authorsList" />
    <MainPage @genresStart="setGenresList" :genre="selectValue" @authorStart="setAuthorList"
      :author="selectValueAuthor" />
  </div>
</template>

<script>
import HeaderPage from "./components/HeaderPage.vue";
import MainPage from "./components/MainPage.vue";

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
      selectValueAuthor: '',
      authorsList: [],
    }
  },
  methods: {
    setGenre(value) {
      this.selectValue = value;
    },
    setGenresList(value) {
      this.genresList = value;
    },
    setAuthor(value) {
      this.selectValueAuthor = value;
    },
    setAuthorList(value) {
      this.authorsList = value;
    }
  }
}
</script>

<style lang="scss">
@import "./assets/scss/style.scss";
</style>