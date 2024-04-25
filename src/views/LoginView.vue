<script setup>
import { ref } from 'vue'
import LoginForm from '../components/Auth/LoginForm/LoginForm.vue'
import { login } from '@/api/user'
import { useRouter } from 'vue-router'

const isLoading = ref(false)
const handleLogin = async (userData) => {
  try {
    await login(userData)
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
  <LoginForm @submit="handleLogin" :is-loading="isLoading" />
</template>
