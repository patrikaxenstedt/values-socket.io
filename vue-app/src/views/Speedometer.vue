<template>
  <div class="speedometer">
    <h1>Speedometer</h1>
    <speedometer :speedValue="speedometerValue" />
  </div>
</template>

<script>
import Speedometer from '@/components/Speedometer';

export default {
  components: {
    Speedometer
  },
  created() {
    this.sockets.subscribe('newSpeedometerValue', value => {
      this.speedometerValue = value;
    });
  },
  data() {
    return {
      speedometerValue: 0
    };
  }
};
</script>
