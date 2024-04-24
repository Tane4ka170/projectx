<script setup>
import { reactive, toRaw } from 'vue'
import IButton from '@/components/IButton/IButton.vue'
import IInput from '@/components/IInput/IInput.vue'

const emit = defineEmits(['submit'])
const userData = reactive({
  name: '',
  email: '',
  password: ''
})

const props = defineProps({
  isLoading: {
    default: false,
    type: Boolean
  }
})
</script>

<template>
  <form @submit.prevent="emit('submit', toRaw(userData))">
    <IInput label="Повне ім'я" class="mb-4" v-model="userData.name" />
    <IInput label="Електронна пошта" placeholder="email@gmail.com" v-model="userData.email" />
    <IInput label="Пароль" type="password" v-model="userData.password" />
    <IButton class="mt-5" variant="gradient" type="submit" :is-loading="props.isLoading"
      >Створити аккаунт</IButton
    >
  </form>
</template>
