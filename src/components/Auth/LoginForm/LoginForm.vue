<script setup>
import { reactive } from 'vue'
import FormContainer from '../FormContainer.vue'
import IInput from '@/components/IInput/IInput.vue'
import IButton from '@/components/IButton/IButton.vue'
const emit = defineEmits(['submit'])
const userData = reactive({
  email: '',
  password: ''
})
</script>

<template>
  <FormContainer @submit.prevent="emit('submit', userData)">
    <IInput class="mb-4" v-model="userData.email" placeholder="Електронна пошта" />
    <IInput type="password" v-model="userData.password" placeholder="Пароль" />
    <IButton class="mt-5" variant="gradient" type="submit">Увійти</IButton>
  </FormContainer>
</template>
