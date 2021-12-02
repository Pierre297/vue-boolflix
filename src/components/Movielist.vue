<template>
  <div>
    <Moviecard v-for="(movie, i) in movies" :key="i" :moviedetails="movie" />
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
    };
  },

  created() {
    this.getMovies();
  },
  computed: {},

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
</style>
