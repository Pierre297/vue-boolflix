<template>
  <div class="card-container">
    <div class="card">
      <img
        class="movie-poster"
        :src="moviePoster(moviedetails)"
        :alt="moviedetails.title"
      />
      <div class="overlay text">
        <h2>{{ moviedetails.title }}</h2>
        <h3>{{ moviedetails.original_title }}</h3>
        <span
          ><img
            class="flag"
            :src="flagLanguage(moviedetails)"
            :alt="moviedetails.original_language"
        /></span>
        <div>{{ moviedetails.vote_average }}</div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Moviecard",

  props: {
    moviedetails: Object,
  },
  methods: {
    // bandiere lingua
    flagLanguage(element) {
      if (element.original_language === "en") {
        return "https://www.countryflags.com/wp-content/uploads/united-kingdom-flag-png-large.png";
      } else {
        return "https://today.uic.edu/files/2015/11/Flag_of_France.png";
      }
    },
    // poster card
    moviePoster(element) {
      if (element.poster_path !== null) {
        return `https://image.tmdb.org/t/p/w342${element.poster_path}`;
      }
      // else if (element.poster_path == null) {
      //   return;
      // }
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.card-container {
  width: calc((100% / 5) - 20px);
  margin: 10px;
}
.card {
  color: white;
  border: 2px solid white;
  // display testo
  position: relative;

  h2 {
    margin: 15px;
  }
}
.flag {
  width: 30px;
  margin: 20px;
}
.movie-poster {
  width: 100%;
  // display testo
  display: block;
  width: 100%;
  height: auto;
}
// display testo
.overlay {
  position: absolute;
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
  height: 100%;
  width: 100%;
  opacity: 0;
  transition: 0.5s ease;
  background-color: #434343;
}

.card:hover .overlay {
  opacity: 1;
  cursor: pointer;
}

.text {
  color: white;
  font-size: 20px;
  position: absolute;
  top: 50%;
  left: 50%;
  -webkit-transform: translate(-50%, -50%);
  -ms-transform: translate(-50%, -50%);
  transform: translate(-50%, -50%);
  text-align: center;
}
</style>
