<script setup lang="ts">
import { Chart, ArcElement, Tooltip, Legend } from 'chart.js';
import { Doughnut, reactive, ref, onMounted } from 'vue';

Chart.register(ArcElement, Tooltip, Legend);

const chartData = reactive({
      labels: ['VueJs', 'EmberJs', 'ReactJs', 'AngularJs'],
      datasets: [
        {
          backgroundColor: ['#41B883', '#E46651', '#00D8FF', '#DD1B16'],
          data: [40, 20, 80, 10],
        },
      ],
    });

    const chartOptions = reactive({
      responsive: true,
    });

    const chartRef = ref(null);

    onMounted(() => {
      const ctx = chartRef.value.getContext('2d');
      new Chart(ctx, {
        type: 'doughnut',
        data: chartData,
        options: chartOptions,
      });
    });


</script>

<template>
    <DoughnutChart :data="chartData" :options="chartOptions" />
</template>


