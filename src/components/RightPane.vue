<template>
  <div class="w-64 space-y-8">
    <div
      v-for="(pane, index) in rightPane"
      class="flex justify-between items-end"
      :class="index === 4 ? 'pt-14' : ''"
    >
      <div class="flex flex-col space-y-2">
        <span class="text-xs text-white"> {{ pane.title }} </span>
        <div class="relative w-36 h-1.5">
          <div class="w-36 absolute left-0 top-0 rounded-full h-1.5 bg-gray-600/20"></div>
          <div
            class="absolute left-0 top-0 bg-blue rounded-full h-1.5"
            :style="`width:${pane.percentage}%`"
          />
        </div>
      </div>
      <div class="pl-4 text-lg font-medium text-white whitespace-nowrap">
        {{ pane.value }} {{ pane.unit }}
      </div>
    </div>
  </div>
</template>

<script>
const rightPane = [
  {
    title: "Inertial Velocity",
    value: 7.68,
    unit: " km/s",
    percentage: 80,
  },
  {
    title: "Altitude",
    value: 390.0,
    unit: " km",
    percentage: 30,
  },
  {
    title: "Apogee",
    value: 404.4,
    unit: " km",
    percentage: 40,
  },
  {
    title: "Perigee",
    value: 389.4,
    unit: " km",
    percentage: 70,
  },
  {
    title: "Inclination",
    value: 51.67,
    unit: "°",
    percentage: 75,
  },
  {
    title: "Range to ISS",
    value: 0.02,
    unit: " km",
    percentage: 95,
  },
];
export default {
  setup() {
    return {
      rightPane,
    };
  },
};
</script>
