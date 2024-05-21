<template>
    <div class="shoe-list">
      <h1>Aokiji Shoes</h1>
      <div class="shoe-items">
        <ShoeItem 
          v-for="shoe in shoes" 
          :key="shoe.id" 
          :shoe="shoe"
          @showDetail="handleShowDetail" 
        />
      </div>
    </div>
  </template>
  
  <script setup>
  import ShoeItem from './ShoeItem.vue';
  
  const props = defineProps({
    shoes: Array
  });
  
  const emit = defineEmits(['showDetail']);
  
  function handleShowDetail(shoe) {
    emit('showDetail', shoe);
  }
  </script>
  
  <style scoped>
  .shoe-list {
    display: flex;
    flex-direction: column;
    align-items: center;
    color:black;
  }
  
  .shoe-items {
    display: flex;
    color:black;
    flex-wrap: wrap;
    gap: 20px;
    justify-content: center;
  }
  
  .shoe-items > * {
    flex: 1 1 calc(25% - 20px); /* 25% width minus gap */
    box-sizing: border-box;
    max-width: 200px;
  }
  </style>
  