<template>
  <div id="app">
    <Header />
  </div>
</template>

<script>
import Header from "./components/Header.vue";

export default {
  name: "App",
  components: {
    Header
  },
};

</script>

<style lang="scss">
@import url("https://fonts.googleapis.com/css2?family=Bungee&display=swap");

#app {
  font-family: $baseFont;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
</style>
