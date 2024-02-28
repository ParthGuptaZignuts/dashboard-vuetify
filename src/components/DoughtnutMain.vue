<script setup lang="ts">
import { computed, ref } from "vue";
import { DoughnutChart, useDoughnutChart } from "vue3-charts";
import { Chart, ChartData, ChartOptions, registerables } from "chartjs";

Chart.register(...registerables);

const dataValues = ref([30, 40, 60, 70, 5]);
    const toggleLegend = ref(true);

    const testData = computed<ChartData<"doughnut">>(() => ({
      labels: ["Paris", "Nîmes", "Toulon", "Perpignan", "Autre"],
      datasets: [
        {
          data: dataValues.value,
          backgroundColor: [
            "#77CEFF",
            "#0079AF",
            "#123E6B",
            "#97B0C4",
            "#A5C8ED",
          ],
        },
      ],
    }));

    const options = computed<ChartOptions<"doughnut">>(() => ({
      scales: {
        myScale: {
          type: "logarithmic",
          position: toggleLegend.value ? "left" : "right",
        },
      },
      plugins: {
        legend: {
          position: toggleLegend.value ? "top" : "bottom",
        },
        title: {
          display: true,
          text: "Chart.js Doughnut Chart",
        },
      },
    }));

    const { doughnutChartProps} = useDoughnutChart({
      chartData: testData,
      options,
    });

</script>

<template>
  <DoughnutChart v-bind="doughnutChartProps" />
</template>
