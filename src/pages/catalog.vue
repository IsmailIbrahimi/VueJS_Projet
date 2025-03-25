<template>
  <div class="catalog-container">
    <h2>Catalogue</h2>
    <div class="product-list">
      <div class="product-card" v-for="product in products" :key="product.id">
        <h3>{{ product.name }}</h3>
        <p>{{ product.price }} €</p>
        <button @click="addToCart(product)">Ajouter au panier</button>
      </div>
    </div>
  </div>
</template>


<script setup lang="ts">
import { ref } from 'vue'
import { useCartStore } from '../stores/cartStore'

const cartStore = useCartStore()

const products = ref([
  { id: 1, name: 'T-shirt Vue.js', price: 20 },
  { id: 2, name: 'Casquette Vite', price: 15 },
  { id: 3, name: 'Mug Pinia', price: 10 },
])

const addToCart = (product: any) => {
  cartStore.add(product)
}
</script>