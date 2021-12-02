<template>
  <div>
    <form action="">
      <input type="text" v-model="inputText" />
      <button>Search</button>
    </form>
  </div>
</template>

<script>
export default {
  name: "Navbar",

  data() {
    return {
      searchbar: "",
      inputText: "",
      searchText: "",
    };
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
input {
  margin: 30px;
}
</style>
