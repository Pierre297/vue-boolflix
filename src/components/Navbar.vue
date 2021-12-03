<template>
  <div class="searchbar">
    <form action="">
      <input type="text" v-model="inputText" />
      <button @click.prevent="$emit('search', searchText)">Search</button>
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
    };
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.searchbar {
  margin: 60px;

  input {
    height: 30px;
  }
  button {
    height: 30px;
  }
}
</style>
