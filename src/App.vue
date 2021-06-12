<template>
  <div id="app">
    <img alt="Vue logo" :src="productLogo" />
    <div>{{ product }}</div>
  </div>
</template>

<script>
import Image from "./assets/logo.png";

export default {
  name: "App",
  data: () => {
    return {
      product: "Socks",
      productLogo: Image,
    };
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
