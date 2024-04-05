<script setup>
const props = defineProps({
  label: String
})
</script>

<template>
  <div class="w-full text-[#2c2c2c]">
    <label class="block">
      <span class="block text-xs px-3 mb-2">{{ props.label }}</span>
      <input
        class="w-full text-sm rounded-[4px] border-[1px] py-2 px-3 border-[#eaeaea] focus:outline-primary"
        type="text"
      />
    </label>
  </div>
</template>
