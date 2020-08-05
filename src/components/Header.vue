<template>
  <div id="header">
    <header class="navigation">
      <show-at breakpoint="mediumAndBelow">
        <button class="mobile-menu" v-on:click="openMenu">
          <img
            src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAADAAAAAwCAYAAABXAvmHAAAABmJLR0QA/wD/AP+gvaeTAAAAP0lEQVRoge3WIQ4AIBADsIP//xk0CYaEMEErpza3KgAgp22y8bzFmaVzT7W4xQAASPKF0gwAgCRfKM0AAOBnEzhSAxbF826PAAAAAElFTkSuQmCC"
          />
          <span class="u-hide">Menu</span>
        </button>
      </show-at>
      <show-at breakpoint="large">
        <div class="headerMenu">
          <div class="headerMenu-item">
            <a href="/" class="headerMenu-link">The Sofa</a>
          </div>
          <div class="headerMenu-item">
            <a href="/" class="headerMenu-link">Reviews</a>
          </div>
          <div class="headerMenu-item">
            <a href="/" class="headerMenu-link">About Us</a>
          </div>
        </div>
      </show-at>
      <a href="/" class="headerLogo">
        <img svg-inline class="headerLogo-image" alt="Allday logo" src="../assets/allday-logo.svg" />
      </a>
      <show-at breakpoint="large">
        <div class="headerMenu">
          <div class="headerMenu-item -right">
            <a href="/" class="headerMenu-link">Showroom</a>
          </div>
          <div class="headerMenu-item -right">
            <a href="/" class="headerMenu-link">Swatches</a>
          </div>
        </div>
      </show-at>
    </header>
    <show-at breakpoint="mediumAndBelow">
      <MobileMenu :is-active="isActive" />
    </show-at>
  </div>
</template>

<script>
import MobileMenu from "../components/MobileMenu.vue";
import { showAt } from "vue-breakpoints";

export default {
  name: "Header",
  components: {
    MobileMenu,
    showAt,
  },
  data: function () {
    return { isActive: false };
  },
  methods: {
    openMenu: function () {
      this.isActive ? (this.isActive = false) : (this.isActive = true);
      this.$emit('menu-open', this.isActive);
    },
  },
};
</script>

<style lang="scss" scoped>
#header {
  margin-bottom: 2.25rem;
}

.navigation {
  padding: 2rem;
  position: relative;
}

.mobile-menu {
  border: none;
  background: transparent;
  display: inline-block;
  position: absolute;
  top: 50%;
  transform: translateY(-50%);
}

.headerLogo {
  margin-right: auto;
  margin-left: auto;
  display: block;
  width: 45%;
  max-width: 20rem;
}

.headerLogo-image {
    width: 100%;
}

.headerMenu {
  display: flex;
  align-items: center;
}

.headerMenu-item {
  margin-right: 1.5rem;
  &.-right {
    margin-left: 1.5rem;
  }
}

.headerMenu-link {
  border-bottom: 3px none $lightBlue;
  color: $black;
  font-family: $headline;
  font-size: 1rem;
  text-decoration: none;

  &:hover {
    border-bottom: 3px solid $lightBlue;
  }
}

@media (min-width: 1128px) {
  .navigation {
    display: flex;
    justify-content: space-between;
    padding: 2.25rem;
  }
}
</style>
