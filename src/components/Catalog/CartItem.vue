<template>
  <div class="cart__item">
    <div class="name">{{ cart__item_data.name }}</div>
    <div class="email">{{ cart__item_data.email }}</div>
    <div class="address">{{ cart__item_data.address.street }}</div>
    <div class="address">{{ cart__item_data.phone }}</div>
    <div class="cart__quantity">
      <div><b>Qty:</b></div>
      {{ cart__item_data.quantity }}
    </div>
    <button class="del" @click="deleteFromCart">Delete</button>
  </div>
</template>

<script>
export default {
  props: {
    cart__item_data: {
      type: Object,
      default() {
        return {};
      },
    },
  },
  mounted() {
    this.$set(this.cart__item_data, "quantity", 1);
  },
  methods:{
    deleteFromCart(){
      this.$emit('deleteFromCart')
    }
  }
};
</script>

<style>
.cart__item {
  margin: 25px auto;
  padding: 15px;
  box-shadow: 0px 0px 5px 5px #f3f3f3;
}
.del {
  background-color: red;
}
</style>
