<template>
  <div class="small">
    <line-chart :chart-data="chartData" :option="options" />
  </div>
</template>

<script>
import LineChart from '@/components/charts/LineChart.js';
export default {
  name: 'Chart',
  components: {
    LineChart
  },
  props: ['chartData'],
  data() {
    return {
      options: {
        scales: {
          xAxes: [
            {
              display: true,
              scaleLabel: {
                display: true,
                labelString: 'Fetched values'
              }
            }
          ],
          yAxes: [
            {
              display: true,
              ticks: {
                beginAtZero: true,
                steps: 10,
                stepValue: 5,
                max: 100
              }
            }
          ]
        }
      }
    };
  }
};
</script>
<style scoped>
.small {
  max-width: 800px;
  margin: 50px auto;
}
</style>
