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

      <div class="add-to-cart-section">
        <button class="add-item-btn" @click="addToCart">Add</button>
        <span>Added: {{ numberItemsAddedToCart }}</span>
      </div>
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
      numberItemsAddedToCart: 0,
    };
  },
  methods: {
    addToCart() {
      return this.numberItemsAddedToCart++;
    },
  },
};
</script>

<style lang="scss">
:root {
  --background-color: #ffe5e5;
  --color: #000000;
  --feedback-bg-color: #ffffff;
  --feedback-secondary-color: #ffacac;
  --feedback-primary-color: #53488d;
  --feedback-icon-color: #ffffff;
  --feedback-form-input: #f4f4f4;
}

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

  .add-to-cart-section {
    display: flex;
    flex-direction: row;
    justify-content: space-between;

    .add-item-btn {
      padding: 0.2em 1em;
      cursor: pointer;

      border: none;
      background-color: var(--feedback-secondary-color);
      color: var(--feedback-primary-color);
      transition: all 0.3s;

      &:hover {
        background-color: var(--background-color);
      }
    }
  }
}
</style>
