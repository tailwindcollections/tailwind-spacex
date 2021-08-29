<template>
  <div class="flex justify-center space-x-4">
    <Stat v-for="stats in topStats" :stats="stats" />
  </div>
</template>

<script>
import Stat from "./Stat.vue";
const topStats = [
  {
    title: "Ppo2",
    value: "2.69",
    unit: "psia",
    gauge: 61,
  },
  {
    title: "Cabin temp",
    value: "2.41",
    unit: "°C",
    gauge: 20,
  },
  {
    title: "Cabin pressure",
    value: "14.00",
    unit: "psia",
    gauge: 61,
  },
  {
    title: "Co2",
    value: "0.07",
    unit: "mmHg",
    gauge: 80,
  },
];
export default {
  components: { Stat },
  setup() {
    return {
      topStats,
    };
  },
};
</script>
