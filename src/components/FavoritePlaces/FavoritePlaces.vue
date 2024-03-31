<script setup>
import FavoritePlace from '../FavoritePlace/FavoritePlace.vue'
import IButton from '../IButton/IButton.vue'
</script>

<template>
  <div class="px-6">
    <div class="text-grey mb-4">Додані маркери</div>
    <slot name="label"></slot>
    <slot name="list">
      <FavoritePlace v-for="n in 4" :key="n" />
    </slot>
    <IButton class="w-full mt-10">Додати Маркер</IButton>
  </div>
</template>
