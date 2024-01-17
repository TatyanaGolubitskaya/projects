<script setup>
defineProps({
  totalPrice: Number
})

const emit = defineEmits(['openDrawer'])
</script>

<template>
  <header class="flex justify-between border-b border-slate-200 px-10 py-8">
    <router-link to="/">
      <div class="flex items-center gap-4">
        <img src="../../public/logo.png" alt="Logo" class="w-10" />
        <div>
          <h2 class="text-xl font-bold uppercase">vueshop</h2>
        </div>
      </div></router-link
    >
    <div class="flex items-center gap-10">
      <div
        @click="() => emit('openDrawer')"
        class="flex items-center cursor-pointer gap-3 text-gray-500 hover:text-black"
      >
        <img src="../../public/cart.svg" alt="Cart" />
        <b>{{ totalPrice }} ₽</b>
      </div>
      <router-link to="/favorites">
        <div class="flex items-center cursor-pointer gap-3 text-gray-500 hover:text-black">
          <img src="../../public/heart.svg" alt="Favorites" />
          <span>Favorites</span>
        </div>
      </router-link>
      <div class="flex items-center cursor-pointer gap-3 text-gray-500 hover:text-black">
        <img src="../../public/profile.svg" alt="Profile" />
        <span>Profile</span>
      </div>
    </div>
  </header>
</template>
