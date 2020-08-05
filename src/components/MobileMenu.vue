<template>
  <div id="mobileMenu" :class="{active: isActive}">
    <div class="mobileMenu-element">
      <a href="/" class="mobileMenu-link">The Sofa</a>
    </div>
    <div class="mobileMenu-element">
      <a href="/" class="mobileMenu-link">Reviews</a>
    </div>
    <div class="mobileMenu-element">
      <a href="/" class="mobileMenu-link">About Us</a>
    </div>
    <div class="mobileMenu-element">
      <a href="/" class="mobileMenu-link">Showroom</a>
    </div>
    <div class="mobileMenu-element">
      <a href="/" class="mobileMenu-link">Swatches</a>
    </div>
  </div>
</template>

<script>
export default {
  name: "MobileMenu",
  props: ["isActive"],
};
</script>

<style lang="scss" scoped>
#mobileMenu {
  background-color: $background;
  border-top: 1px solid $gray;
  height: 100vh;
  overflow-y: auto;
  position: fixed;
  right: 0;
  text-align: center;
  top: 6.5rem;
  transform: translateX(-100%);
  transition: transform 0.4s ease-in;
  width: 100vw;
  z-index: 2;
}

#mobileMenu.active {
  transform: translateX(0);
}

.mobileMenu-element {
  border-bottom: 1px solid $gray;
}

.mobileMenu-link {
  font-family: $headline;
  display: block;
  color: $black;
  padding: 1rem;
  text-decoration: none;
  width: 100%;
  height: 100%;

  &:hover {
    color: $blue;
    transition: color 0.2s ease-in;
  }
}
</style>
