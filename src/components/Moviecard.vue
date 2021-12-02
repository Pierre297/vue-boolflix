<template>
  <div class="card-container">
    <div class="card">
      <img :src="moviedetails.poster_path" :alt="moviedetails.title" />
      <h2>{{ moviedetails.title }}</h2>
      <span>{{ moviedetails.overview }}</span>
      <div>{{ moviedetails.release_date }}</div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Moviecard",

  props: {
    moviedetails: Object,
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
</style>
