<template>
  <div id="app">
    <Header 
      :genres="allGenres" 
      :authors="allAuthors"
      :appGenre="currentGenre"
      :appAuthor="currentAuthor"
      @changedGenre="updateSelectedGenre" 
      @changedAuthor="updateSelectedAuthor"
    />

    <Main 
      :selectedGenre="currentGenre"
      :selectedAuthor="currentAuthor"
      @dataReady="setData" 
    />
  </div>
</template>

<script>
import Header from './components/Header';
import Main from './components/Main';

export default {
  name: 'App',
  data: function() {
    return {
      allGenres: [],
      allAuthors: [],
      currentGenre: '',
      currentAuthor: ''
    }
  },
  methods: {
    setData: function(genresArray, authorsArray) {
      this.allGenres = genresArray;
      this.allAuthors = authorsArray;
    },
    updateSelectedGenre: function(newGenre) {
      this.currentGenre = newGenre;
      this.currentAuthor = "";
    },
    updateSelectedAuthor: function(newAuthor) {
      this.currentAuthor = newAuthor;
      this.currentGenre = "";
    }
  },
  components: {
    Header,
    Main
  }
}
</script>

<style lang="scss">
@import './assets/styles/general';
</style>
