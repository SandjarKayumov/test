<template>
  <div class="catalog__items">
    <div class="catalog__item">
      <div class="name">{{ product__data.name }}</div>
      <div class="email">{{ product__data.email }}</div>
      <div class="address">{{ product__data.address.street }}</div>
      <button class="btn_cart" @click="addToCart">Add To Cart</button>
    </div>
  </div>
</template>

<script>
export default {
  name: "CatalogItem",
  props: {
    product__data: {
      type: Object,
      default() {
        return {};
      },
    },
  },
  methods: {
    addToCart() {
      this.$emit("addToCart", this.product__data);
      console.log("Cart");
    },
  },
};
</script>

<style lang="scss">
.catalog__items {
  // border: 1px solid #000;
  width: 250px;
  height: 300px;
  margin-bottom: 20px;

  .catalog__item {
    padding: 10px;
    box-shadow: 0px 0px 5px 5px #f3f3f3;
  }
  .name {
    font-weight: bold;
  }
  .email {
    color: rgb(92, 92, 255);
  }
  .address {
    color: #2c2c2c;
  }
  .btn_cart {
    background-color: #ff7900;
    margin-top: 180px;
  }
}
</style>
