<template>
  <div class="main">
    <div class="wrapper">
      <!-- <router-view></router-view> -->
      <!--  <Cart v-if="CART.length" :cart__data="CART" />
      <Catalog /> -->
    </div>
  </div>
</template>

<script>
import { mapGetters } from "vuex";
/* import Catalog from "@/components/Catalog/Catalog.vue";
import Cart from "@/components/Catalog/Cart.vue"; */
export default {
  name: "Main",
  components: {
    /*  Catalog,
    Cart, */
  },
  computed: {
    ...mapGetters(["CART"]),
  },
};
</script>

<style>
.wrapper {
  max-width: 1400px;
  margin: 0 auto;
}
* {
  /* outline: 1px solid red; */
}
</style>
