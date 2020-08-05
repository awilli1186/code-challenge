<template>
  <div id="main">
    <div class="mainItem">
      <div class="mainItem-small">
        <div class="shipping">
            <img svg-inline class="shipping-icon" src="../assets/padlock.svg" alt="padlock" />
            Secure Checkout
        </div>
        <div>Ships in 5-7 business days</div>
      </div>
      <ul class="images">
        <li class="images-image" :class="{'-active': activeImage(0)}">
          <img src="../assets/sofa/sofa-amber.jpg" alt="Amber sofa" />
        </li>
        <li class="images-image" :class="{'-active': activeImage(1)}">
          <img src="../assets/sofa/sofa-charcoal.jpg" alt="Charcoal sofa" />
        </li>
        <li class="images-image" :class="{'-active': activeImage(2)}">
          <img src="../assets/sofa/sofa-red.jpg" alt="Red sofa" />
        </li>
      </ul>
      <show-at breakpoint="mediumAndAbove">
        <Highlights />
      </show-at>
    </div>
    <div class="mainItem">
      <h1 class="heading">The Sofa</h1>
      <p
        class="description"
      >Lorem ipsum dolor sit amet, consectetur adipiscing elit. Donec ac dui interdum, tincidunt velit sit amet.</p>
      <div class="pricing">
        <div class="pricing-column">
          <span>Pay Now</span>
          <span class="pricing-price">$1,250</span>
          <span class="strike">$1,450</span>
          <small>$200 OFF with code</small>
        </div>
        <div class="pricing-column">
          <span>Pay as low as</span>
          <span class="pricing-price">
            $25/
            <span>month</span>
          </span>
          <span>with Klarna</span>
          <small>
            <a href="/">Learn More</a>
          </small>
        </div>
      </div>
      <button class="addToCart">Add to cart</button>
      <div class="saveLink">
        <a href="/" class="saveLink-link">Save design for later</a>
      </div>
      <Selector :active-index="activeIndex" @update-active="updateActive" />
    </div>
    <show-at breakpoint="mediumAndBelow">
        <Highlights />
    </show-at>
  </div>
</template>

<script>
import Selector from "./Selector.vue";
import Highlights from "./Highlights.vue";
import { showAt } from "vue-breakpoints";

export default {
  name: "Main",
  components: {
      Selector,
      Highlights,
      showAt
  },
  data: function () {
    return { activeIndex: 0 };
  },
  methods: {
      activeImage: function(index) {
          if (index !== this.activeIndex) {
              return false;
          }

          return true;
      },
      updateActive: function(index) {
          this.activeIndex = index;
      }
  },
};
</script>

<style lang="scss" scoped>
#main {
    display: grid;
    grid-template-columns:  minmax(0, 1fr);
    padding: 0 2.25rem 3rem;
}

.mainItem-small {
  display: flex;
  justify-content: space-between;
}

.heading {
  color: $blue;
  font-family: $headline;
  font-size: 2.5rem;
  margin-bottom: 0.5rem;
}

.description {
  margin-bottom: 1rem;
}

.pricing {
  display: flex;
  margin-bottom: 1.75rem;
  text-align: center;
}

.pricing-column {
  display: flex;
  font-size: 1.25rem;
  flex-direction: column;
  width: 50%;

  &:first-child {
    border-right: 2px solid $white;
  }
}

.pricing-column small {
  font-size: 0.8rem;
}

.pricing-price {
  font-size: 2.25rem;
  color: $red;
  font-weight: bold;
}

.addToCart {
  cursor: pointer;
  font-family: $headline;
  font-size: 1.25rem;
  width: 100%;
  color: $white;
  background-color: $lightBlue;
  border: 1px solid $lightBlue;
  border-radius: 6px;
  padding: 0.8rem 0;
  margin-bottom: 1rem;
  transition: background-color 0.2s ease-in;

  &:hover {
    background-color: $blue;
  }
}

.saveLink {
  margin-bottom: 2.5rem;
  position: relative;
  text-align: center;
}

.saveLink-link {
    font-family: $headline;
    border-bottom: 3px solid $blue;
    color: $black;
    text-decoration: none;
}

.shipping {
    display: flex;
    align-items: center;
}

.shipping-icon {
    margin-right: .5rem;
}

.images {
    height: 0;
    margin-bottom: 1rem;
    overflow: hidden;
    padding-top: 9px / 16px * 100%;
    position: relative;
}

.images-image {
    position: absolute;
    top: 0;
    left: 0;

    &.-active {
        z-index: 1;
    }
}

.images-image img {
    width: 100%;
    height: 100%;
}

@media (min-width: 1128px) {
    #main {
        grid-template-columns: 2fr 1fr;
        grid-gap: 0 2.25rem;
    }
}
</style>
