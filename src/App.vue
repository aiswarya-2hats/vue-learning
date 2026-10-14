<script setup>
import { ref } from 'vue'
import testimage from '../src/assets/images/image.jpeg'

const title = ref('Hello World')
const description = ref('This is a description')
const image = ref(testimage)
const url = ref('https://www.shutterstock.com/discover/free-nature-images')
const testimagealt = ref('test image')
const isActive = ref(true)
const style = ref({ color: 'red' })
const stock = ref(100)
const details = ref(['Product 1', 'Product 2', 'Product 3'])
const product = ref([
  { id: 1, color: 'red' },
  { id: 2, color: 'blue' },
])
</script>

<template>
  <div>
    <h1>{{ title }}</h1>
    <p>{{ description }}</p>
    <img :src="image" :alt="testimagealt" />
    <a :href="url" target="_blank">Shutterstock</a>
    <div :class="{ active: isActive }">This is a div</div>
    <span :style="{ color: style.color }">This is a span</span>
    <p v-if="stock > 10">In Stock</p>
    <p v-else-if="stock <= 10 && stock > 0">Low Stock</p>
    <p v-else>Out of Stock</p>
    <ul>
      <li v-for="detail in details" :key="detail">{{ detail }}</li>
    </ul>
    <ul>
      <li v-for="product in product" :key="product.id">{{ product.color }}</li>
    </ul>
  </div>
</template>

<style scoped>
h1 {
  color: white;
}
p {
  color: rgb(30, 155, 30);
}
a :hover {
  cursor: pointer;
}
.active {
  color: blue;
}
</style>
