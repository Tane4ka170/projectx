<script setup>
import FavoritePlace from '../FavoritePlace/FavoritePlace.vue'
import IButton from '../IButton/IButton.vue'
import { ref } from 'vue'
import IInput from '../IInput/IInput.vue'

const buttonVariant = ref('gradient')
const changeButtonVariant = () => {
  buttonVariant.value = buttonVariant.value === 'gradient' ? 'outlined' : 'gradient'
}
</script>

<template>
  <div class="px-6">
    <div class="text-grey mb-4">Додані маркери</div>
    <div class="px-5">
      <IInput label="some label"
    </div>
    <slot name="label"></slot>
    <slot name="list">
      <FavoritePlace v-for="n in 4" :key="n" />
    </slot>
    <IButton class="w-full mt-10" :variant="buttonVariant" @click="changeButtonVariant"
      >Додати маркер</IButton
    >
  </div>
</template>
