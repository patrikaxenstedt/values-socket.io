<template>
  <div>
    <vue-speedometer
      :width="500"
      :value="speedValue"
      :maxValue="100"
      currentValueText="Current speed"
      needleTransition="easeElastic"
      needleColor="black"
      textColor="#d8dee9"
    />
  </div>
</template>

<script>
import VueSpeedometer from 'vue-speedometer';

export default {
  name: 'Speedometer',
  components: { VueSpeedometer },
  props: ['speedValue'],
  watch: {
    speedValue: value => {
      console.log('Current speed: ' + value);
    }
  }
};
</script>
