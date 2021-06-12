<template>
  <div id="app">
    <div>
      <ProductCard></ProductCard>
    </div>
  </div>
</template>

<script>
import ProductCard from "@/components/ProductCard/ProductCard.vue";

export default {
  name: "App",
  components: {
    ProductCard,
  },
};
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 60px;

  > div {
    max-width: 920px;
    display: flex;
    justify-content: center;
  }
}
</style>
