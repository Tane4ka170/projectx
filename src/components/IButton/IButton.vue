<script setup>
import { defineProps, computed, toRefs } from 'vue'

const props = defineProps({
  variant: {
    default: 'primary',
    type: String,
    validator: (value) => {
      return ['primary', 'gradient', 'outlined'].includes(value)
    }
  }
})

const { variant } = toRefs(props)
const bgStyles = computed(() => {
  return variant.value === 'gradient'
    ? 'bg-gradient-to-r from-[#FFA279] to-[#F3743D]'
    : 'bg-[#FFA279]'
})
</script>

<template>
  <button class="rounded-xl py-3 px-10 text-white font-bold -tracking-wider" :class="bgStyles">
    <slot></slot>
  </button>
</template>
