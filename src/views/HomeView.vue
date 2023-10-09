<script setup lang="ts">
import ProfileCard from '@/components/ProfileCard.vue'
import EventsHistory from '@/components/EventsHistory.vue'
import CatCharts from '@/components/CatCharts.vue'
import Divider from 'primevue/divider'
</script>

<template>
  <div class="profile-wrapper">
    <ProfileCard />
    <EventsHistory />
    <Divider />
    <CatCharts />
  </div>
</template>

<style scoped>
.profile-wrapper {
  display: flex;
  align-items: flex-start;
  justify-content: space-around;
  flex-wrap: wrap;
}
</style>
