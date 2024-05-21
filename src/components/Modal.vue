<template>
    <div class="modal-overlay" @click.self="close">
      <div class="modal-content">
        <slot></slot>
        <button @click="close">Close</button>
      </div>
    </div>
  </template>
  
  <script setup>
  const emit = defineEmits(['close']);
  
  function close() {
    emit('close');
  }
  </script>
  
  <style scoped>
  .modal-overlay {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: rgba(0, 0, 0, 0.5);
    display: flex;
    justify-content: center;
    align-items: center;
  }
  
  .modal-content {
    background: white;
    color:black;
    padding: 20px;
    border-radius: 8px;
    width: 80%;
    max-width: 500px;
  }
  </style>
  