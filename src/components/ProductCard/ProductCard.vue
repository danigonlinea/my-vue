<template>
  <div class="product-card">
    <div class="product-main"><img alt="Vue logo" :src="productLogo" /></div>
    <div class="product-info">
      <h1>{{ product }}</h1>
      <p v-if="inventory > 10">Available</p>
      <p v-else-if="inventory > 0 && inventory <= 10">
        Almost Sold Out, {{ inventory }} left!
      </p>
      <p v-else>Out of Stock</p>

      <ul class="product-aspects">
        <li :key="detail" v-for="detail in details">
          {{ detail }}
        </li>
      </ul>
    </div>
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
      details: ["80% cotton", "20% polyester", "Gender-neutral"],
    };
  },
};
</script>

<style lang="scss">
.product-card {
  display: grid;
  grid-template-columns: 1fr 1fr;
  padding: 1em;
  box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2), 0 6px 20px 0 rgba(0, 0, 0, 0.19);
  border-radius: 1%;
}

.product-info {
  > div {
    display: flex;
    justify-content: flex-start;
  }

  .product-aspects {
    list-style-type: none;
  }
}
</style>
