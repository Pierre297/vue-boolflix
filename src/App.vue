<template>
  <div id="app"></div>
</template>

<script>
import Header from "./components/Header.vue";
import Movielist from "@/components/Movielist.vue";

export default {
  name: "App",
  components: {
    Header,
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
  color: #2c3e50;
  margin-top: 60px;
}
</style>
