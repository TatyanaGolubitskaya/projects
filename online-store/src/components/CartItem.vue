<script setup>
const emit = defineEmits(['onClickRemove'])

defineProps({
  id: Number, // идентификатор карточки
  title: String, // заголовок карточки
  imageUrl: String, // ссылка на изображение карточки
  price: Number // цена карточки
})
</script>

<template>
  <div class="flex items-center border border-slate-200 p-4 rounded-xl gap-4">
    <img class="w-16 h-16" :src="imageUrl" :alt="title" />

    <div class="flex flex-col flex-1">
      <p>{{ title }}</p>

      <div class="flex justify-between mt-2">
        <b class="flex-1">{{ price }} ₽</b>

        <!-- кнопка удаления из корзины -->
        <img
          @click="emit('onClickRemove')"
          class="opacity-40 hover:opacity-100 cursor-pointer transition"
          src="../../public/close.svg"
        />
      </div>
    </div>
  </div>
</template>
