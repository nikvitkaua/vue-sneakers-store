<script setup>
  import CardItem from './CardItem.vue';

  const onClickAdd = () => {
    alert(111)
  }
</script>


<template>
  <div class="grid grid-cols-2 gap-5">
    <CardItem 
      title="Men's Nike Blazer Mid Suede Sneakers" 
      imageUrl="/sneakers/sneakers-1.jpg" 
      :price="1550"
      :isAdded="false"
      :isFavorite="true"
      :onClickAdd="onClickAdd" 
    />
  </div>
</template>