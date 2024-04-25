<script setup>
import { reactive } from 'vue'

import IInput from '@/components/IInput/IInput.vue'
import IButton from '@/components/IButton/IButton.vue'

const props = defineProps({
  isLoading: {
    default: false,
    type: Boolean
  }
})
const emit = defineEmits(['submit'])
const userData = reactive({
  email: '',
  password: ''
})
</script>

<template>
  <form @submit.prevent="emit('submit', userData)">
    <IInput class="mb-4" v-model="userData.email" label="Електронна пошта" />
    <IInput type="password" v-model="userData.password" label="Пароль" />
    <IButton class="mt-5" variant="gradient" type="submit" :is-loading="props.isLoading"
      >Увійти</IButton
    >
  </form>
</template>
