<template>
  <div id="app">
    <header>
      <h1>BOOLFLIX</h1>
      <Navbar @search="inputButton" />
    </header>
    <main>
      <Movielist :searchbar="searchText" />
    </main>
  </div>
</template>

<script>
import Navbar from "./components/Navbar.vue";
import Movielist from "@/components/Movielist.vue";

export default {
  name: "App",
  components: {
    Navbar,
    Movielist,
  },
  props: {
    searchbar: String,
  },
  data() {
    return {
      searchText: "",
      inputText: "",
    };
  },
  computed: {},
  methods: {
    inputButton() {
      this.searchText = this.inputText;
      console.log(this.searchText);
    },
  },
};
</script>

<style 
@import '~@fortawesome/fontawesome-free/scss/fontawesome'; 
lang="scss">
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  background-color: #434343;
}
header {
  background-color: #000000;
  height: 150px;
  display: flex;
  justify-content: space-between;

  h1 {
    color: #e10000;
    margin: 60px;
  }
}
</style>
