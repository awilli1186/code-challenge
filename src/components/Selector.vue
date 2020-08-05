<template>
    <div id="selector">
        <h2 class="heading">1. Choose a Fabric</h2>
        <p class="description">Choose your choice from fabrics to leather.</p>
        <div class="fabrics">
            <h3 class="fabrics-heading">Fabric Choices</h3>
            <div class="fabrics-inner">
                <button class="fabrics-button" :class="{'-active': activeIndex === 0}" @click="onClickButton(0)">
                    <img class="fabrics-image" src="../assets/sofa/sofa-amber.jpg" alt="amber sofa button">
                    <span class="fabrics-name">Amber</span>
                </button>
                <button class="fabrics-button" :class="{'-active': activeIndex === 1}" @click="onClickButton(1)">
                    <img class="fabrics-image" src="../assets/sofa/sofa-charcoal.jpg" alt="charcoal sofa button">
                    <span class="fabrics-name">Charcoal</span>
                </button>
                <button class="fabrics-button" :class="{'-active': activeIndex === 2}" @click="onClickButton(2)">
                    <img class="fabrics-image" src="../assets/sofa/sofa-red.jpg" alt="red sofa button">
                    <span class="fabrics-name">Red</span>
                </button>
            </div>
        </div>
    </div>
</template>

<script>

export default {
    name: "Selector",
    props: ["activeIndex"],
    methods: {
        onClickButton (index) {
        this.$emit('update-active', index)
        }
    }
};
</script>

<style lang="scss" scoped>
#selector {
    border-top: 2px solid $white;
    padding-top: 1.875rem;
}

.heading {
    color: $blue;
    font-family: $headline;
    font-size: 1rem;
}

.description {
    margin-bottom: 1.75rem;
}

.fabrics {
    margin-bottom: 2rem;
}

.fabrics-heading {
    margin-bottom: 1rem;
}

.fabrics-inner {
    display: flex;
    justify-content: space-between;
}

.fabrics-button {
    background-clip: padding-box;
    background-color: $mediumGray;
    border: none;
    border-radius: 6px;
    cursor: pointer;
    padding: 0;
    width: 30%;

    &.-active {
        background-color: $lightBlue;
        border: 2px solid $lightBlue;

        .fabrics-name {
            color: $white;
        }
    }
}

.fabrics-image {
    border-radius: 6px 6px 0 0;
}

.fabrics-name {
    display: block;
    padding: .75rem 0;
    width: 100%;
}
</style>
