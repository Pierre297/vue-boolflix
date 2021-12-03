<template>
  <div class="card-container">
    <div class="card">
      <!-- <img :src="moviedetails.poster_path" :alt="moviedetails.title" /> -->
      <h2>{{ seriedetails.name }}</h2>
      <h3>{{ seriedetails.original_name }}</h3>
      <span
        ><img
          class="flag"
          :src="flagLanguage(seriedetails)"
          :alt="seriedetails.original_language"
      /></span>
      <div>{{ seriedetails.vote_average }}</div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Seriescard",

  props: {
    seriedetails: Object,
  },
  methods: {
    flagLanguage(element) {
      if (element.original_language === "en") {
        return "https://www.countryflags.com/wp-content/uploads/united-kingdom-flag-png-large.png";
      } else {
        return "https://today.uic.edu/files/2015/11/Flag_of_France.png";
      }
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
  height: 500px;

  h2 {
    margin: 15px;
  }
  div {
    margin: 20px;
  }
}
.flag {
  width: 30px;
  margin: 20px;
}
</style>