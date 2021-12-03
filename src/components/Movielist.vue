<template>
  <div class="movie-container">
    <div class="movie-card">
      <Moviecard v-for="(movie, i) in movies" :key="i" :moviedetails="movie" />
      <Seriescard
        v-for="(serie, tv) in series"
        :key="tv"
        :seriedetails="serie"
      />
    </div>
  </div>
</template>

<script>
import axios from "axios";
import Moviecard from "@/components/Moviecard.vue";
import Seriescard from "@/components/Seriescard.vue";

export default {
  name: "Movielist",

  components: {
    Moviecard,
    Seriescard,
  },

  props: {
    searchbar: String,
    movies: Array,
  },

  data() {
    return {
      apiUrlMovies:
        "https://api.themoviedb.org/3/search/movie?api_key=2f4f5117825f869acb512d659eb0281c&language=en-US&query=a&page=1&include_adult=false",

      series: [],
      searchText: "",
    };
  },

  created() {
    this.getMovies();
    this.getSeries();
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
      axios.get(this.apiUrlMovies).then((result) => {
        this.movies = result.data.results;
      });
    },
    getSeries() {
      axios.get(this.apiUrlSeries).then((result) => {
        this.series = result.data.results;
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
