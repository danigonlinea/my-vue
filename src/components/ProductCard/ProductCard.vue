<template>
  <div>
    <img alt="Vue logo" :src="productLogo" />
    <div>{{ product }}</div>
    <div v-if="inventory > 10">Available</div>
    <div v-else-if="inventory > 0 && inventory <= 10">
      Almost Sold Out, {{ inventory }} left!
    </div>
    <div v-else>Out of Stock</div>
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
      inventory: 0,
    };
  },
};
</script>

<style></style>
