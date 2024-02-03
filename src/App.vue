<script setup>
import { onMounted, ref, computed } from 'vue';
import axios from 'axios';

import MainHeader from './components/MainHeader.vue';
import CardList from './components/CardList.vue';
import DrawerApp from './components/DrawerApp.vue';

const items = ref([]);
const selectedOption = ref('name');
const searchQuery = ref('');

onMounted(async () => {
  try {
    const { data } = await axios.get('../sneakers-data.json');
    
    items.value = data;
  } catch (err) {
    console.log(err)
  }
});

const filteredItems = computed(() => {
  const sortedItems = [...items.value];

  const sortByOption = (a, b) => {
    if (selectedOption.value === "price-low") {
      return a.price - b.price;
    } else if (selectedOption.value === "price-high") {
      return b.price - a.price;
    } else {
      return a.title.localeCompare(b.title);
    }
  };

  sortedItems.sort(sortByOption);

  return sortedItems.filter(item =>
    item.title.toLowerCase().includes(searchQuery.value.toLowerCase())
  );
});

const onChangeSelect = (event) => {
  selectedOption.value = event.target.value;
};

</script>

<template>
  <!-- <DrawerApp /> -->

  <div class="bg-white w-4/5 m-auto rounded-xl shadow-xl mt-14">
    <MainHeader />

    <div class="p-10">
      <div class="flex justify-between items-center mb-8">
        <h2 class="text-3xl font-bold">All sneakers</h2>

        <div class="flex gap-4">
          <select
            @change="onChangeSelect" 
            class="py-2 px-2 border rounded-md outline-none cursor-pointer"
          >
            <option value="name">Name</option>
            <option value="price-low">Price (low)</option>
            <option value="price-high">Price (high)</option>
          </select>

          <div class="relative">
            <img class="absolute top-3 left-4" src="/search.svg" alt="search icon">
            <input
              v-model="searchQuery" 
              type="text"
              placeholder="Search..."
              class="border rounded-md py-2 pl-12 pr-4 outline-none focus:border-gray-400"
            >
          </div>
        </div>
      </div>


      <CardList :items="filteredItems" />
    </div>
  </div>
</template>

<style scoped>
</style>
