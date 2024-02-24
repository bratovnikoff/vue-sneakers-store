<script setup>
import AppCard from './AppCard.vue'

defineProps({ items: Array, isFavorites: Boolean })

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
      :onCLickFavorite="isFavorites ? null : () => emit('addToFavorite', item)"
      :onCLickAdd="isFavorites ? null : () => emit('addToCart', item)"
    />
  </div>
</template>
