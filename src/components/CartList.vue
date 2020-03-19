<template>
<div class="wrapper">
  <div class="cart">
    <div class="product" v-for="product in cart" :key="product.id">
      <div class="info">
        <h1>{{product.name}}</h1>
      </div>
      <div class="image">
        <img :src="'/images/products/'+product.image">
      </div>
      <div class="price">
        <h2>{{product.price}}</h2>
        <button v-on:click="removeFromCart(product)" class="auto">Remove</button>
      </div>
    </div>
  </div>
</div>
</template>

<script>
export default {
  name: 'CartList',
  props: {
    cart: Array
  },
  methods: {
    removeFromCart(product) {
      var index = this.$root.$data.cart.indexOf(product);
      if (index > -1)
      this.$root.$data.cart.splice(index,1);
    }
  }
}
</script>

<style scoped>
.wrapper {
  display: flex;
  align-items: center;
  justify-content: center;
}

.cart {
  margin-top: 10px;
  display: flex;
  flex-wrap: wrap;
  justify-content: space-around;
}

.product {
  margin: 20px;
  margin-top: 25px;
  width: 150px;
}

.product img {
  border: 2px solid #333;
  height: 190px;
  width: 150px;
  object-fit: cover;
}

.product .image {
  display: flex;
  justify-content: center;
  margin-bottom: 5px;
}

.info {
  background: #336699;
  color: #000;
  padding: 5px 15px;
  height: 60px;
}

.info h1 {
  font-size: 16px;
}

.info h2 {
  font-size: 14px;
}

.info p {
  margin: 0px;
  font-size: 10px;
}


.price {
  display: flex;
  color: white;
}

button {
  font-size: 12px;
  height: 50px;
  background: #737373;
  color: white;
  border: none;
}

.auto {
  margin-left: auto;
}
</style>
