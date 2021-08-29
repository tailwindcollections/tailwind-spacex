<template>
  <div
    class="relative flex items-center justify-center bg-white rounded-[10px] bg-opacity-[0.02]"
    :class="size === 'md' ? 'w-[160px] h-[175px]' : 'w-[130px] h-[140px]'"
  >
    <svg
      class="absolute"
      :height="size == 'md' ? 138 : 110"
      :width="size == 'md' ? 138 : 110"
      viewBox="0 0 152 152"
      fill="none"
    >
      <path
        class="stroke-current"
        :class="gaugeColor === 'text-red' ? 'text-red' : 'text-gray-600'"
        d="M29.1016 134.528C16.9571 124.797 8.14045 111.528 3.87378 96.5623C-0.392887 81.5961 0.101713 65.6733 5.28903 51.0008C10.4763 36.3283 20.0995 23.6328 32.8246 14.674C45.5497 5.71507 60.7466 0.936531 76.309 1.00064C91.8713 1.06474 107.028 5.96832 119.679 15.0317C132.33 24.0952 141.848 36.8695 146.915 51.5842C151.981 66.299 152.344 82.2253 147.954 97.1558C143.565 112.086 134.639 125.282 122.415 134.913"
        stroke-dasharray=".5 3"
      />
      <path
        class="stroke-current"
        :class="gaugeColor === 'text-red' ? 'text-red' : 'text-gray-600'"
        d="M30.3523 132.967C18.5315 123.495 9.95004 110.581 5.79715 96.014C1.64426 81.4469 2.12567 65.9487 7.17466 51.6675C12.2236 37.3862 21.5901 25.0293 33.9759 16.3093C46.3617 7.58934 61.1534 2.93822 76.3007 3.00062C91.4481 3.06302 106.201 7.83583 118.514 16.6576C130.828 25.4793 140.092 37.913 145.023 52.2353C149.955 66.5577 150.308 82.0593 146.036 96.5917C141.763 111.124 133.075 123.967 121.177 133.342"
        stroke-width="6"
        stroke-dasharray="1 42 1 225 1 40 1 40"
        stroke-dashoffset="-24"
      />
      <path
        class="stroke-current"
        :class="gaugeColor"
        d="M30.3523 132.967C18.5315 123.495 9.95004 110.581 5.79715 96.014C1.64426 81.4469 2.12567 65.9487 7.17466 51.6675C12.2236 37.3862 21.5901 25.0293 33.9759 16.3093C46.3617 7.58934 61.1534 2.93822 76.3007 3.00062C91.4481 3.06302 106.201 7.83583 118.514 16.6576C130.828 25.4793 140.092 37.913 145.023 52.2353C149.955 66.5577 150.308 82.0593 146.036 96.5917C141.763 111.124 133.075 123.967 121.177 133.342"
        stroke-width="6"
        :stroke-dasharray="strokeDashArray"
        stroke-dashoffset="0"
      />
    </svg>
    <div class="flex flex-col items-center justify-center pt-3 text-white">
      <span class="uppercase" :class="size === 'md' ? 'text-xxs' : 'text-xxxs'">
        {{ stats.title }}
      </span>
      <span class="leading-tight" :class="size === 'md' ? 'text-3xl' : 'text-2xl'">
        {{ stats.value }}
      </span>
      <span class="leading-normal" :class="size === 'md' ? 'text-xl' : 'text-base'">
        {{ stats.unit }}
      </span>
    </div>
  </div>
</template>

<script>
import { computed } from "@vue/reactivity";
export default {
  props: {
    stats: {
      type: Object,
      required: true,
    },
    size: {
      type: String,
      required: false,
      default: "md",
    },
  },

  setup(props) {
    const gauge = props.stats.gauge;

    const gaugeColor = computed(() => {
      if (gauge >= 0 && gauge < 30) {
        return "text-red";
      }
      if (gauge >= 30 && gauge < 80) {
        return "text-yellow";
      }
      return "text-blue";
    });

    const strokeDashArray = computed(() => {
      if (gauge >= 0 && gauge < 30) {
        return `${gauge} 360`;
      }
      if (gauge >= 30 && gauge < 80) {
        return `25 1 ${gauge - 26} 360`;
      }
      return `25 1 40 1 ${gauge - 67} 360`;
    });
    return {
      strokeDashArray,
      gaugeColor,
    };
  },
};
</script>
