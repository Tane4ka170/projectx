<script setup>
import FavoritePlaces from './components/FavoritePlaces/FavoritePlaces.vue'
import OpenLayersMap from './components/OpenLayersMap/OpenLayersMap.vue'
import MarkerIcon from './components/icons/MarkerIcon.vue'

const favoritePlaces = [
  {
    id: 1,
    title: 'New place 1',
    description: 'Super description 1',
    img: '',
    lngLat: [30.5234, 50.4501]
  },
  {
    id: 2,
    title: 'New place 2',
    description: 'Super description 2',
    img: '',
    lngLat: [30.5367, 50.4422]
  }
]

const markers = favoritePlaces.map((place) => ({
  title: place.title,
  lngLat: place.lngLat
}))
</script>

<template>
  <main class="flex h-screen">
    <div class="bg-white h-full w-[400px] shrink-0 overflow-auto pb-10">
      <FavoritePlaces :items="favoritePlaces" />
    </div>
    <div class="w-full h-full flex items-center justify-center text-6xl">
      <OpenLayersMap
        class="w-full h-full"
        :center="[30.5233, 50.4501]"
        :zoom="15"
        :markers="markers"
      >
      </OpenLayersMap>
    </div>
  </main>
</template>
