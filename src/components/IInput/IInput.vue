<script setup>
// import { ref } from 'vue'

const props = defineProps({
  modelValue: String,
  label: String,
  placeholder: String,
  type: {
    default: 'text',
    type: String
  }
})

defineOptions({
  inheritAttrs: false
})

// const text = ref('')
// const changeText = (event) => {
//   text.value = event.target.value
// }

const emit = defineEmits(['update:modelValue'])
</script>

<template>
  <div class="w-full text-[#2c2c2c]">
    <label class="block">
      <span class="block text-xs px-3 mb-2">{{ props.label }}</span>
      <input
        class="w-full text-sm rounded-[4px] border-[1px] py-2 px-3 border-[#eaeaea] focus:outline-primary"
        v-bind="{ ...$props, ...$attrs }"
        :value="modelValue"
        @input="emit('update:modelValue', $event.target.value)"
      />
    </label>
  </div>
</template>
