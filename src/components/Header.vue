<template>
  <header class="d-flex justify-content-between px-3">
      <div>
          <img src="../assets/img/spotify-logo.png" alt="Logo Spotify">
      </div>
      <div>
          <select
            v-model="selectedGenre"
            @change="$emit('changedGenre', selectedGenre)"
          >
              <option value="">Seleziona un genere</option>
              <option
               v-for="(genre, index) in genres"
               :key="index" 
               :value="genre">
                {{ genre }}
              </option>
          </select>

          <select class="ms-2"
             v-model="selectedAuthor"
             @change="$emit('changedAuthor', selectedAuthor)"   
          >
              <option value="">Seleziona un autore</option>
              <option 
                v-for="(author, index) in authors"
                :key="index"
                :value="author">
                {{ author }}
              </option>
          </select>
      </div>
  </header>
</template>

<script>
export default {
    name: "Header",
    data: function() {
        return {
            selectedGenre: '',
            selectedAuthor: ''
        }
    },
    watch: {
       appGenre: function(val) {
           this.selectedGenre = val;
       },
        appAuthor: function(val) {
           this.selectedAuthor = val;
       }
    },
    props: {
        "genres": Array,
        "authors": Array,
        "appGenre": String,
        "appAuthor": String
    }
}
</script>

<style lang="scss" scoped>
    @import '../assets/styles/variables';

    header {
        height: 70px;
        line-height: 70px;
        background-color: $light-color;

        img {
            width: 50px;
        }

        select {
            padding: 5px;
        }
    }
</style>