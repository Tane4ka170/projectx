<script setup>
import { reactive, toRaw } from 'vue'
import IButton from '@/components/IButton/IButton.vue'
import IInput from '@/components/IInput/IInput.vue'
import FormContainer from '../FormContainer.vue'

const emit = defineEmits(['submit'])
const userData = reactive({
  name: '',
  email: '',
  password: ''
})
</script>

<template>
  <FormContainer
    class="max-w-[500px] w-full bg-white p-10 rounded-2xl"
    @submit.prevent="emit('submit', toRaw(userData))"
  >
    <IInput label="Повне ім'я" class="mb-4" v-model="userData.name" />
    <IInput label="Електронна пошта" placeholder="email@gmail.com" v-model="userData.email" />
    <IInput label="Пароль" type="password" disabled v-model="userData.password" />
    <IButton class="mt-5" variant="gradient" type="submit">Створити аккаунт</IButton>
  </FormContainer>
</template>
