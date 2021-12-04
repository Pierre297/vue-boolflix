<template>
  <div id="app">
    <header>
      <h1>BOOLFLIX</h1>
      <Navbar @search="inputButton" />
    </header>
    <main>
      <Movielist :searchbar="searchText" :movies="movies" />
    </main>
  </div>
</template>

<script>
import axios from "axios";
import Navbar from "./components/Navbar.vue";
import Movielist from "@/components/Movielist.vue";

export default {
  name: "App",
  components: {
    Navbar,
    Movielist,
  },
  props: {
    searchbar: String,
  },
  data() {
    return {
      searchText: "",
      inputText: "",
      // API movies
      baseUrl: "https://api.themoviedb.org/3/search/",
      apiKey: "?api_key=2f4f5117825f869acb512d659eb0281c",
      language: "&language=en-US",
      movies: [],
      // API series
      baseUrlTv: "https://api.themoviedb.org/3/search/",
      tvSeries: [],
    };
  },
  computed: {},
  methods: {
    inputButton(param) {
      this.searchText = param;
      console.log(this.searchText);
      this.getFilms();
    },
    getFilms() {
      let url =
        this.baseUrl +
        "movie" +
        this.apiKey +
        this.language +
        "&query=" +
        this.searchText;
      console.log(url);
      axios.get(url).then((result) => {
        this.movies = result.data.results;
        console.log(this.movies);
      });
    },
    getSeries() {
      let url =
        this.baseUrlTv +
        "movie" +
        this.apiKey +
        this.language +
        "&query=" +
        this.searchText;
      console.log(url);
      axios.get(url).then((result) => {
        this.movies = result.data.results;
        console.log(this.movies);
      });
    },
  },
};
</script>

<style
lang="scss">
@import "~@fortawesome/fontawesome-free/scss/fontawesome";
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
body {
  background-color: #434343;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  background-color: #434343;
}
header {
  background-color: #000000;
  height: 150px;
  display: flex;
  justify-content: space-between;

  h1 {
    color: #e10000;
    margin: 60px;
  }
}
</style>
