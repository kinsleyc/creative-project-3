<template>
  <div>
    <div class="wrapper">
      <h1>Cart</h1>
    </div>
    <div class="empty">
      <p v-show="this.$root.$data.cart.length === 0">The cart is currently empty.</p>
    </div>
    <CartList :cart="cart" />
  </div>
</template>

<script>
import CartList from "../components/CartList.vue"
export default {
  name: 'Cart',
  components: {
    CartList
  },
  data() {
    return {
    }
  },
  computed: {
    cart() {
      return this.$root.$data.cart;
    }
  },
};
</script>

<style scoped>
.wrapper {
  display: flex;
  align-items: center;
  justify-content: center;
}
.empty {
  display: flex;
  align-items: center;
  justify-content: center;
}
</style>
