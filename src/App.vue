<template>
  <div id="app" :class="{active: isActive}">
    <Header @menu-open="fixBody"/>
    <Main />
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import Main from "./components/Main.vue";

export default {
  name: "App",
  components: {
    Header,
    Main,
  },
    data: function () {
    return { isActive: false };
  },
  methods: {
    fixBody: function (active) {
      this.isActive = active;
    }
  }

};
</script>

<style lang="scss">
@import url("https://fonts.googleapis.com/css2?family=Bungee&display=swap");

#app {
  height: 100vh;
}

.active {
  position: fixed;
}
</style>
