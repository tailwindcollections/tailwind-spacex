<template>
  <div class="grid grid-cols-5 gap-4 pt-4">
    <Stat
      v-for="(stats, index) in bottomStats"
      :stats="stats"
      :class="index === 2 ? 'col-start-4' : ''"
      size="sm"
    />
  </div>
</template>

<script>
import Stat from "./Stat.vue";
const bottomStats = [
  {
    title: "Loop A",
    value: "26.53",
    unit: "°C",
    gauge: 135,
  },
  {
    title: "Loop B",
    value: "20.00",
    unit: "°C",
    gauge: 180,
  },
  {
    title: "NET PWR 1",
    value: "0.00",
    unit: "W",
    gauge: 0,
  },
  {
    title: "NET PWR 2",
    value: "0.00",
    unit: "W",
    gauge: 0,
  },
];

export default {
  components: { Stat },
  setup() {
    return {
      bottomStats,
    };
  },
};
</script>
