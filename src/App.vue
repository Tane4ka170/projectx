<script setup>
import FavoritePlaces from './components/FavoritePlaces/FavoritePlaces.vue'
import OpenLayersMap from './components/OpenLayersMap/OpenLayersMap.vue'
</script>

<template>
  <main class="flex h-screen">
    <div class="bg-white h-full w-[400px] shrink-0 overflow-auto pb-10">
      <FavoritePlaces />
    </div>
    <div class="w-full h-full flex items-center justify-center text-6xl">
      <OpenLayersMap class="w-full h-full" :center="[30.5233, 50.4501]" :zoom="15"></OpenLayersMap>
    </div>
  </main>
</template>
