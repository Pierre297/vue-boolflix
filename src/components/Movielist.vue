<template>
  <div class="movie-container">
    <div class="movie-card">
      <Moviecard
        v-for="(movie, i) in filteredMovies"
        :key="i"
        :moviedetails="movie"
      />
    </div>
  </div>
</template>

<script>
import axios from "axios";
import Moviecard from "@/components/Moviecard.vue";

export default {
  name: "Movielist",

  components: {
    Moviecard,
  },

  props: {
    searchbar: String,
  },

  data() {
    return {
      apiUrl:
        "https://api.themoviedb.org/3/search/movie?api_key=2f4f5117825f869acb512d659eb0281c&language=en-US&query=house&page=1&include_adult=false",
      movies: [],
      searchText: "",
    };
  },

  created() {
    this.getMovies();
  },
  computed: {
    filteredMovies() {
      if (this.searchbar === "") {
        return this.movies;
      }

      return this.movies.filter((item) => {
        return item.original_title
          .toLowerCase()
          .includes(this.searchText.toLowerCase());
      });
    },
  },

  methods: {
    getMovies() {
      axios.get(this.apiUrl).then((result) => {
        this.movies = result.data.results;
      });
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.movie-container {
  width: 95%;
  margin: 20px auto;
}
.movie-card {
  margin-top: 20px;
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
}
</style>
