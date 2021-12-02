<template>
  <div>
    <div class="movie-card">
      <h3>{{ moviedetails.title }}</h3>
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
.movie-card {
  color: white;
}
</style>
