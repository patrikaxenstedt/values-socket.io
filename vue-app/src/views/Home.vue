<template>
  <div class="home">
    <chart :chart-data="chartData" />
  </div>
</template>

<script>
import Chart from '@/components/Chart';

export default {
  name: 'Home',
  components: {
    Chart
  },
  created() {
    this.sockets.subscribe('newChartData', data => {
      this.fillData(data);
    });
  },
  data() {
    return {
      chartData: {}
    };
  },
  methods: {
    fillData(values) {
      this.chartData = {
        labels: values,
        datasets: [
          {
            label: 'Values from socket.io',
            backgroundColor: '#f87979',
            data: values
          }
        ]
      };
    }
  }
};
</script>
