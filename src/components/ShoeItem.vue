<template>
    <div @click="showDetail">
      <img :src="shoe.image" :alt="shoe.name" />
      <h3>{{ shoe.name }}</h3>
      <p>{{ shoe.price }}</p>
    </div>
  </template>
  
  <script setup>
  const props = defineProps({
    shoe: Object
  });
  
  const emit = defineEmits(['showDetail']);
  
  function showDetail() {
    emit('showDetail', props.shoe);
  }
  </script>
  
  <style scoped>
  div {
    border: 1px solid #ddd;
    padding: 10px;
    cursor: pointer;
    display: flex;
    flex-direction: column;
    align-items: center;
    width: 200px;
  }
  
  img {
    width: 100%;
    height: auto;
    display: block;
    margin-bottom: 10px;
  }
  </style>
  