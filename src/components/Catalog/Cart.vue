<template>
  <div class="cart">
    <router-link :to="{ name: 'Catalog' }">
      <div class="catalog__cart">Back to Catalog</div>
    </router-link>
    <h3>Cart</h3>
    <CartItem
      v-for="(item, index) in cart__data"
      :key="item.id"
      :cart__item_data="item"
      @deleteFromCart="deleteFromCart(index)"
    />
  </div>
</template>

<script>
import CartItem from "@/components/Catalog/CartItem.vue";
import { mapActions } from "vuex";
export default {
  name: "Cart",
  props: {
    cart__data: {
      type: Array,
      default() {
        return [];
      },
    },
  },
  methods: {
    ...mapActions(["DELETE_FROM_CART"]),
    deleteFromCart(index) {
      this.DELETE_FROM_CART(index);
    },
  },
  components: {
    CartItem,
  },
};
</script>

<style></style>
