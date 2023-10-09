<script setup lang="ts">
import { ref, onMounted } from 'vue'
import Chart from 'primevue/chart'

onMounted(() => {
  chartData.value = setChartData()
  chartOptions.value = setChartOptions()
})

const chartData = ref()
const chartOptions = ref()

const setChartData = () => {
  const documentStyle = getComputedStyle(document.documentElement)

  return {
    labels: [
      '09:00',
      '10:00',
      '11:00',
      '12:00',
      '13:00',
      '14:00',
      '15:00',
      '16:00',
      '17:00',
      '18:00',
      '19:00',
      '20:00',
      '21:00',
      '22:00'
    ],
    datasets: [
      {
        label: 'Number of birds eaten',
        backgroundColor: documentStyle.getPropertyValue('--blue-500'),
        borderColor: documentStyle.getPropertyValue('--blue-500'),
        data: [2, 0, 0, 0, 0, 0, 1, 2, 0, 0, 0, 0, 0, 1, 2, 0, 0, 0, 0, 0, 1]
      },
      {
        label: 'Number of active minutes',
        backgroundColor: documentStyle.getPropertyValue('--pink-500'),
        borderColor: documentStyle.getPropertyValue('--pink-500'),
        data: [28, 48, 40, 19, 16, 0, 20, 40, 19, 16, 0, 20, 40, 19, 16, 0, 20]
      }
    ]
  }
}
const setChartOptions = () => {
  const documentStyle = getComputedStyle(document.documentElement)
  const textColor = documentStyle.getPropertyValue('--text-color')
  const textColorSecondary = documentStyle.getPropertyValue('--text-color-secondary')
  const surfaceBorder = documentStyle.getPropertyValue('--surface-border')

  return {
    maintainAspectRatio: false,
    aspectRatio: 0.8,
    plugins: {
      legend: {
        labels: {
          fontColor: textColor
        }
      }
    },
    scales: {
      x: {
        ticks: {
          color: textColorSecondary,
          font: {
            weight: 500
          }
        },
        grid: {
          display: false,
          drawBorder: false
        }
      },
      y: {
        ticks: {
          color: textColorSecondary
        },
        grid: {
          color: surfaceBorder,
          drawBorder: false
        }
      }
    }
  }
}
</script>

<template>
  <Chart type="bar" :data="chartData" :options="chartOptions" class="profile-chart" />
</template>

<style scoped>
.profile-chart {
  height: 30rem;
  width: 100%;
}
</style>
