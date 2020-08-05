<template>
  <div id="productHighlights">
    <img svg-inline class="" src="../assets/free-shipping.svg" alt="free shipping" />
    <img svg-inline class="" src="../assets/trial.svg" alt="365 day trial" />
    <img svg-inline class="" src="../assets/made-in-america.svg" alt="made in america" />
    <img svg-inline class="" src="../assets/warranty.svg" alt="10 year warranty" />
    <img svg-inline class="" src="../assets/assembly.svg" alt="easy to assemble" />
    <img svg-inline class="" src="../assets/materials.svg" alt="quality materials" />
  </div>
</template>

<script>

export default {
  name: "Highlights",
};
</script>

<style lang="scss" scoped>
#productHighlights {
    align-items: center;
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    position: relative;
    }

@media (min-width: 1128px) {
    #productHighlights {
        flex-wrap: initial;
        justify-content: space-between;
    }
}
</style>
