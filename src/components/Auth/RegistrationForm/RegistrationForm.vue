<script setup>
import IInput from '@/components/IInput/IInput.vue'
</script>

<template>
  <form class="max-w-[500px] w-full bg-white p-10 rounded-2xl">
    <IInput label="Повне ім'я" class="mb-4" />
    <IInput label="Електронна пошта" placeholder="email@gmail.com" />
    <IInput label="Пароль" type="password" disabled />
  </form>
</template>
