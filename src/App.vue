<script setup>
import MainHeader from './components/MainHeader.vue';
import CardList from './components/CardList.vue';
import DrawerApp from './components/DrawerApp.vue';
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
            class="py-2 px-2 border rounded-md outline-none"
          >
            <option>Name</option>
            <option>Price (low)</option>
            <option>Price (high)</option>
          </select>

          <div class="relative">
            <img class="absolute top-3 left-4" src="/search.svg" alt="search icon">
            <input 
              type="text"
              placeholder="Search..."
              class="border rounded-md py-2 pl-12 pr-4 outline-none focus:border-gray-400"
            >
          </div>
        </div>
      </div>


      <CardList />
    </div>
  </div>
</template>

<style scoped>
</style>
