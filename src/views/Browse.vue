<template>
<div>
  <div class="pure-menu pure-menu-horizontal">
    <ul class="pure-menu-list">
      <li class="pure-menu-item"><a @click="select('supplement')" href="#" class="pure-menu-link">Supplements</a></li>
      <li class="pure-menu-item"><a @click="select('vitamin')" href="#" class="pure-menu-link">Vitamins</a></li>
    </ul>
  </div>
  <ProductList :products="products" />
</div>
</template>

<script>
import ProductList from "../components/ProductList.vue"
export default {
  name: 'Browse',
  components: {
    ProductList
  },
  data() {
    return {
      type: '',
    }
  },
  computed: {
    products() {
      return this.$root.$data.products.filter(product => product.type === this.type);
    }
  },
  methods: {
    select(type) {
      this.type = type;
    }
  },
}
</script>
