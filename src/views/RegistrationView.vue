<script setup>
import RegistrationForm from '../components/Auth/RegistrationForm/RegistrationForm.vue'
import { registrUser } from '@/api/user'
import { useRouter } from 'vue-router'

const handleSubmit = async (userData) => {
  isLoading.value = true
  try {
    await registrUser(userData)
    router.replace('/map')
  } catch (error) {
    console.error(error)
  } finally {
    isLoading.value = false
  }
}

const router = useRouter()
</script>

<template>
  <RegistrationForm @submit="handleSubmit" :isLoading="isLoading" />
</template>
