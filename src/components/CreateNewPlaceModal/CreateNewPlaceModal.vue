<script setup>
import { computed, reactive } from 'vue'
import IButton from '../IButton/IButton.vue'
import IInput from '../IInput/IInput.vue'
import IModal from '../IModal/IModal.vue'
import InputImage from '../InputImage/InputImage.vue'
import MarkerIcon from '../icons/MarkerIcon.vue'

const props = defineProps({
  isOpen: {
    default: false,
    type: Boolean
  }
})

const emit = defineEmits(['close', 'submit'])
const formData = reactive({
  title: '',
  description: '',
  img: ''
})

const uploadText = computed(() => {
  return formData.img ? 'Натисніть тут, щоб змінити фото' : 'Натисніть тут, щоб додати фото'
})

const handleUpload = (url) => {
  formData.img = url
}
</script>

<template>
  <IModal v-if="props.isOpen" @close="emit('close')">
    <form @submit.prevent="emit('submit', formData)" class="min-w-[420px]">
      <div class="font-bold text-center flex gap-1 justify-center mb-10">
        <MarkerIcon /> Додати маркери
      </div>
      <IInput label="Локація" class="mb-4" v-model="formData.title" />
      <IInput type="textarea" label="Опис" class="mb-3" v-model="formData.description" />
      <div class="flex gap-2 mb-10">
        <img :src="formData.img" alt="avatar" v-if="formData.img" class="w-9 h-9 object-cover" />
        <InputImage @uploaded="handleUpload">{{ uploadText }}</InputImage>
      </div>

      <IButton variant="gradient" class="w-full">Додати</IButton>
    </form>
  </IModal>
</template>
