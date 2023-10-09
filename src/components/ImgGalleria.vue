<script setup lang="ts">
import { ref } from 'vue'
import Galleria from 'primevue/galleria'

const images = ref([
  {
    itemImageSrc:
      'https://koshka.top/uploads/posts/2021-11/1637888701_1-koshka-top-p-britanskaya-koshka-pyatnistaya-1.jpg',
    alt: 'cat'
  },
  { itemImageSrc: 'https://elite-british.by/wp-content/uploads/2019/04/8V5A1037.jpg', alt: 'cat' }
])
const responsiveOptions = ref([
  {
    breakpoint: '991px',
    numVisible: 4
  },
  {
    breakpoint: '767px',
    numVisible: 3
  },
  {
    breakpoint: '575px',
    numVisible: 1
  }
])
</script>

<template>
  <div class="card">
    <Galleria
      :value="images"
      :responsiveOptions="responsiveOptions"
      :numVisible="5"
      containerStyle="max-width: 640px"
      :showThumbnails="false"
      :showIndicators="true"
    >
      <template #item="slotProps">
        <img
          :src="slotProps.item.itemImageSrc"
          :alt="slotProps.item.alt"
          style="width: 100%; display: block; height: 20em"
        />
      </template>
    </Galleria>
  </div>
</template>
