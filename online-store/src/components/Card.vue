<script setup>
// пропсы для карточек
defineProps({
  id: Number, // идентификатор карточки
  title: String, // заголовок карточки
  imageUrl: String, // ссылка на изображение карточки
  price: Number, // цена карточки
  isFavorite: Boolean, // установлен ли карточка в избранное
  isAdded: Boolean, // установлен ли карточка в корзину
  onClickFavorite: Function, // обработчик нажатия на карточку в избранное
  onClickAdd: Function // обработчик нажатия на карточку в корзину
})
</script>

<template>
  <div
    class="relative bg-white border border-slate-100 rounded-3xl p-8 cursor-pointer transition hover:-translate-y-2 hover:shadow-xl"
  >
    <img
      v-if="onClickFavorite"
      :src="!isFavorite ? '/like-1.svg' : '/like-2.svg'"
      alt="Like 1"
      class="absolute top-8 left-8"
      @click="onClickFavorite"
    /><!-- смена кнопки на добавление в избранное -->

    <img :src="imageUrl" alt="Sneaker" />

    <p class="mt-2">{{ title }}</p>
    <!-- название товара -->

    <div class="flex justify-between mt-5">
      <div class="flex flex-col">
        <span class="text-slate-400">Price:</span>
        <b>{{ price }} ₽</b>
        <!-- цена товара -->
      </div>

      <img
        v-if="onClickAdd"
        @click="onClickAdd"
        :src="!isAdded ? '/plus.svg' : '/checked.svg'"
        alt="Plus"
      /><!-- смена кнопки на добавление в корзину -->
    </div>
  </div>
</template>
