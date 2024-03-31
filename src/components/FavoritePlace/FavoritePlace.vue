<script setup>
import FavoritePlaceIconButton from './FavoritePlaceIconButton.vue'
import DeleteIcon from './DeleteIcon.vue'
import EditIcon from './EditIcon.vue'
</script>

<template>
  <section class="text-gray mb-6 last:mb-0">
    <div class="flex gap-4">
      <img src="" alt="" class="w-[76px] h-[76px] shrink-0" />
      <div>
        <div class="flex justify-between items-center mb-2">
          <h2 class="font-bold text-sm text-[#2c2c2c]">Палац Спорту</h2>
          <div class="flex gap-2">
            <FavoritePlaceIconButton><EditIcon /></FavoritePlaceIconButton>
            <FavoritePlaceIconButton><DeleteIcon /></FavoritePlaceIconButton>
          </div>
        </div>
        <p class="text-xs line-clamp-3">
          Київський палац спорту, символ міста та важлива арена для спортивних подій та культурних
          заходів, вражає своєю архітектурою та можливостями, забезпечуючи місцевим та міжнародним
          спортсменам і артистам ідеальну платформу для виступів та змагань.
        </p>
      </div>
    </div>

    <div class="h-[1px] w-full bg-[#ececec] mt-4"></div>
  </section>
</template>
