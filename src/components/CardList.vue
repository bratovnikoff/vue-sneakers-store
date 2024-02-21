<script setup>
import AppCard from './AppCard.vue'

defineProps({ items: Array })

const emit = defineEmits(['addToFavorite', 'addToCart'])
</script>

<template>
  <div class="grid grid-cols-4 gap-5" v-auto-animate>
    <AppCard
      v-for="item in items"
      :key="item.id"
      :id="item.id"
      :title="item.title"
      :image-url="item.imageUrl"
      :price="item.price"
      :isFavorite="item.isFavorite"
      :isAdded="item.isAdded"
      :onCLickFavorite="() => emit('addToFavorite', item)"
      :onCLickAdd="() => emit('addToCart', item)"
    />
  </div>
</template>
