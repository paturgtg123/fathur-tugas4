<template>
    <div>
      <h2>{{ shoe.name }}</h2>
      <img :src="shoe.image" :alt="shoe.name" />
      <p>{{ shoe.description }}</p>
      <p>Harga: {{ shoe.price }}</p>
      <div>
        <label for="quantity">Jumlah: </label>
        <input type="number" id="quantity" v-model.number="quantity" min="1" />
      </div>
      <p>Total Harga: {{ totalPrice }}</p>
      <button @click="buyShoe">Beli</button>
    </div>
  </template>
  
  <script setup>
  import { ref, computed } from 'vue';
  
  const props = defineProps({
    shoe: Object
  });
  
  const quantity = ref(1);
  const totalPrice = computed(() => {
    return quantity.value * parseFloat(props.shoe.price.replace('$', ''));
  });
  
  function buyShoe() {
    alert(`Anda membeli ${quantity.value} ${props.shoe.name} dengan total harga ${totalPrice.value}`);
  }
  </script>
  
  <style scoped>
  div {
    text-align: center;
  }
  
  img {
    width: 100%;
    max-width: 200px;
    height: auto;
    display: block;
    margin-bottom: 10px;
  }
  
  label {
    margin-right: 10px;
  }
  
  input {
    width: 50px;
    margin-bottom: 10px;
  }
  </style>
  