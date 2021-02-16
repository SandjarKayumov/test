<template>
  <div>
    <router-link :to="{ name: 'Cart', params: { cart__data: CART } }">
      <div class="catalog__cart">Cart: {{ CART.length }}</div>
    </router-link>
    <div class="catalog">
      <CatalogItem
        v-for="product in PRODUCTS"
        :key="product.id"
        :product__data="product"
        @addToCart="addToCart"
      />
    </div>
  </div>
</template>

<script>
import { mapActions, mapGetters } from "vuex";
import CatalogItem from "@/components/Catalog/CatalogItem.vue";
export default {
  name: "Catalog",
  computed: {
    ...mapGetters(["PRODUCTS", "CART"]),
  },
  methods: {
    ...mapActions(["GET_PRODUCTS_FROM_API", "ADD_TO_CART"]),
    addToCart(data) {
      this.ADD_TO_CART(data);
    },
  },
  mounted() {
    this.GET_PRODUCTS_FROM_API().then((response) => {
      if (response) {
        console.log("Done");
      }
    });
  },
  components: {
    CatalogItem,
  },
};
</script>

<style>
.catalog__cart {
  margin: 20px 0;
  padding: 10px;
  background: #2c2c2c;
  color: #fff;
  width: 100px;
  position: absolute;
  top: 0;
  right: 25px;
}
.catalog {
  display: flex;
  justify-content: space-evenly;
  align-items: center;
  /* flex-wrap: wrap; */
}
</style>
