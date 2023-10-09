<script setup lang="ts">
import { ref } from 'vue'
import Timeline from 'primevue/timeline'

const events = ref([
  { status: 'Прокинулась', date: '15/10/2020 10:30' },
  { status: 'Поїла', date: '15/10/2020 11:00' },
  { status: 'Гралась', date: '15/10/2020 11:45' },
  { status: 'Заснула', date: '16/10/2020 15:00' }
])
</script>

<template>
  <div class="card">
    <Timeline :value="events">
      <template #opposite="slotProps">
        <small class="p-text-secondary">{{ slotProps.item.date }}</small>
      </template>
      <template #content="slotProps">
        {{ slotProps.item.status }}
      </template>
    </Timeline>
  </div>
</template>
