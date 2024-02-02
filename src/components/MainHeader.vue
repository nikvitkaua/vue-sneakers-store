<template>
  <header 
    class="flex justify-between border-b border-slate-200 px-10 py-8"
  >
    <div class="flex items-center gap-4">
      <img src="/logo.png" alt="logo" class="w-10">
      <div>
        <h2 class="text-xl font-bold uppercase">Vue Sneakers</h2>
        <p class="text-slate-400">Best store of sneakers!</p>
      </div>
    </div>

    <ul class="flex items-center gap-10">
      <li class="flex items-center gap-3 text-gray-500 transition hover:text-black cursor-pointer">
        <img src="/cart.svg" alt="cart">
        <b>1200$</b>
      </li>

      <li class="flex items-center gap-3 text-gray-500 hover:text-black cursor-pointer">
        <img src="/heart.svg" alt="cart">
        <span>Bookmarks</span>
      </li>

      <li class="flex items-center gap-3 text-gray-500 hover:text-black cursor-pointer">
        <img src="/profile.svg" alt="cart">
        <span>Log In</span>
      </li>
    </ul>
  </header>
</template>