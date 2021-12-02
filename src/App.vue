<template>
  <div id="app">
    <header>
      <h1>BOOLFLIX</h1>
      <Navbar />
    </header>
    <main>
      <Movielist />
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
};
</script>

<style lang="scss">
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
}
header {
  background-color: #000000;
  height: 150px;
  display: flex;
  justify-content: space-between;

  h1 {
    color: #e10000;
    margin: 30px;
  }
}

main {
  background-color: #434343;
}
</style>
