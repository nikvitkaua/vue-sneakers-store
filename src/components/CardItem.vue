<script setup>
 defineProps({
    imageUrl: String,
    title: String,
    price: Number,
    isFavorite: Boolean,
    isAdded: Boolean,
    onClickAdd: Function,
    onClickFavorite: Function
 });
</script>

<template>
  <div class="relative border bg-white border-slate-100 rounded-2xl p-8 cursor-pointer hover:-translate-y-2 hover:shadow-xl transition">
    <img @click="onClickFavorite" :src="isFavorite ? '/like-2.svg' : '/like-1.svg'" alt="like 1" class="absolute top-2 left-2">
    <img :src="imageUrl" alt="sneaker image">
    <p class="mt-2">{{ title }}</p>

    <div class="flex justify-between mt-5">
      <div class="flex flex-col">
        <span class="text-slate-400">Price:</span>
        <b>{{ price }} $</b>
      </div>

      <img @click="onClickAdd" :src="!isAdded ? '/plus.svg' : '/checked.svg'" alt="plus">
    </div>
  </div>
</template>