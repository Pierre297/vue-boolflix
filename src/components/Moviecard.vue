<template>
  <div>
    <div>
      <h3>{{ moviedetails.title }}</h3>
      <span>{{ moviedetails.overview }}</span>
      <span>{{ moviedetails.release_date }}</span>
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
</style>
