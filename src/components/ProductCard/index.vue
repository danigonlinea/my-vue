<template>
  <div>
    <img alt="Vue logo" :src="productLogo" />
    <div>{{ product }}</div>
  </div>
</template>

<script>
import Image from "@/assets/logo.png";

export default {
  name: "ProductCard",
  data: () => {
    return {
      product: "Socks",
      productLogo: Image,
    };
  },
};
</script>

<style></style>
