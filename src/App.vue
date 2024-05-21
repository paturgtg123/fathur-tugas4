<script setup>
import { ref } from 'vue';
import ShoeList from './components/ShoeList.vue';
import ShoeDetail from './components/ShoeDetail.vue';
import Modal from './components/Modal.vue';

const shoes = ref([
  { id: 1, name: 'Nike', description: 'Comfortable and stylish', price: '$50', image: 'https://i.pinimg.com/236x/b1/d4/73/b1d473bd054486858c8d98634ea02e86.jpg' },
  { id: 2, name: 'Adidas', description: 'Durable and rugged', price: '$80', image: 'https://i.pinimg.com/236x/e4/49/e0/e449e0e6a859db722df9034462317bec.jpg' },
  { id: 3, name: 'Puma', description: 'Light and airy', price: '$30', image: 'https://i.pinimg.com/236x/a7/49/0e/a7490e72d138172532dcd928b985b0bc.jpg' },
  { id: 1, name: 'Reebok', description: 'Comfortable and stylish', price: '$60', image: 'https://i.pinimg.com/236x/b5/cc/a8/b5cca88ad39d55ccdc96a2feef0d565c.jpg' },
  { id: 2, name: 'New Balance', description: 'Durable and rugged', price: '$55', image: 'https://i.pinimg.com/236x/c6/44/2c/c6442ca2b3be29a0bed30f9d1e2f1c1b.jpg' },
  { id: 3, name: 'Converse', description: 'Light and airy', price: '$20', image: 'https://i.pinimg.com/474x/2b/5c/a1/2b5ca109517a8d47516048dfd576ce65.jpg' },
  { id: 1, name: 'Vans', description: 'Comfortable and stylish', price: '$25', image: 'https://i.pinimg.com/236x/0a/83/d7/0a83d7e16f8efe7e165a3f71d4874549.jpg' },
  { id: 2, name: 'Asics', description: 'Durable and rugged', price: '$90', image: 'https://i.pinimg.com/236x/b6/b3/15/b6b315a11a5f08263b387b94447b7c6b.jpg' },
  { id: 3, name: 'Diadora', description: 'Light and airy', price: '$35', image: 'https://i.pinimg.com/236x/29/36/07/2936077b3ad43621510b06d152943ed3.jpg' },
]);

const selectedShoe = ref(null);
const isModalOpen = ref(false);

function handleShowDetail(shoe) {
  selectedShoe.value = shoe;
  isModalOpen.value = true;
}

function closeModal() {
  isModalOpen.value = false;
}
</script>

<template>
  <div>
    <ShoeList :shoes="shoes" @showDetail="handleShowDetail" />
    <Modal v-if="isModalOpen" @close="closeModal">
      <ShoeDetail :shoe="selectedShoe" />
    </Modal>
  </div>
</template>

<style scoped>
div {
  display: flex;
  flex-direction: column;
  align-items: center;
  padding: 20px;
  font-family: stencil;
}
</style>
