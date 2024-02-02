<script setup>
  import CartHeader from './CartHeader.vue';
  import CartItemList from './CartItemList.vue';
</script>

<template>
  <div class="fixed top-0 left-0 h-full w-full bg-black z-10 opacity-70"></div>
  <div class="bg-white w-96 h-full fixed right-0 top-0 z-20 p-8">
    <CartHeader />

    <CartItemList />

    <div class="flex flex-col gap-4 mt-7">
      <div class="flex justify-between gap-2">
        <span>Total:</span>
        <div class="flex-1 border-b border-dashed"></div>
        <b>12900$</b>
      </div>

      <div class="flex justify-between gap-2">
        <span>Tax: 5%</span>
        <div class="flex-1 border-b border-dashed"></div>
        <b>17$</b>
      </div>

      <button 
        class="mt-4 bg-lime-500 w-full rounded-xl py-3 text-white hover:bg-lime-600 transition disabled:bg-slate-400"
      >
        Confirm order
      </button>
    </div>
  </div>
</template>