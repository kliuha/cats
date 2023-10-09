<script setup lang="ts">
import ImgGalleria from './ImgGalleria.vue'
import Card from 'primevue/card'
import Listbox from 'primevue/listbox'

const catCharacteristics = [
  'довжина шерсті: Короткошерстний',
  'колір: Різнобарвний',
  'порода: Британська'
]
</script>

<template>
  <Card class="cat-profile">
    <template #header>
      <ImgGalleria />
    </template>
    <template #title> Британська пятниста </template>
    <template #subtitle>
      <Listbox disabled :options="catCharacteristics" class="w-full md:w-14rem" />
    </template>
    <template #content>
      <p>
        Заводчики кішок цінують британців за спокійний характер і врівноваженість, що доповнюється
        розкішним зовнішнім виглядом і впевненістю в собі. Британські кішки легко приживуться у
        маленькій квартирі сам на сам із господарем і водночас будуть раді великій та гучній родині
        з дітьми. Незворушність, розум і показність – британська порода кішок повністю відповідає
        бездоганній репутації англійця.
      </p>
    </template>
  </Card>
</template>

<style scoped>
.cat-profile,
.cat-img {
  width: 25em;
}
</style>
