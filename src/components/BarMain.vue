<script setup lang="ts">
import { ref } from 'vue';
import { Bar } from 'vue3-chartjs';
import {
  Chart as ChartJS,
  Title,
  Tooltip,
  Legend,
  BarElement,
  CategoryScale,
  LinearScale,
} from 'chart.js';

ChartJS.register(
  Title,
  Tooltip,
  Legend,
  BarElement,
  CategoryScale,
  LinearScale
);

const chartData = ref({
      labels: [
        'January',
        'February',
        'March',
        'April',
        'May',
        'June',
        'July',
        'August',
        'September',
        'October',
        'November',
        'December',
      ],
      datasets: [
        {
          label: 'Data One',
          backgroundColor: '#425C5A',
          data: [40, 20, 12, 39, 10, 40, 39, 80, 40, 20, 12, 11],
        },
      ],
    });

    const chartOptions = ref({
      responsive: true,
    });
</script>

<template>
    <Bar id="my-chart-id" :options="chartOptions" :data="chartData" />
  </template>