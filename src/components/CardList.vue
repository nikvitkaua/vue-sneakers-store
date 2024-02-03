<script setup>
  import CardItem from './CardItem.vue';

  defineProps({
    items: Array
  });

  const onClickAdd = () => {
    alert(111)
  }
</script>


<template>
  <div class="grid grid-cols-2 gap-5">
    <CardItem
      v-for="item in items"
      :key="item.id" 
      :title="item.title" 
      :imageUrl="item.imageUrl" 
      :price="item.price"
      :isAdded="false"
      :isFavorite="false"
      :onClickAdd="onClickAdd" 
    />
  </div>
</template>