<script setup>
import IButton from '@/components/IButton/IButton.vue'
import IInput from '@/components/IInput/IInput.vue'

const emit = defineEmits(['submit'])
</script>

<template>
  <form
    class="max-w-[500px] w-full bg-white p-10 rounded-2xl"
    @submit.prevent="emit('submit', { name: 'NAme' })"
  >
    <IInput label="Повне ім'я" class="mb-4" />
    <IInput label="Електронна пошта" placeholder="email@gmail.com" />
    <IInput label="Пароль" type="password" disabled />
    <IButton class="mt-5" variant="gradient" type="submit">Створити аккаунт</IButton>
  </form>
</template>
