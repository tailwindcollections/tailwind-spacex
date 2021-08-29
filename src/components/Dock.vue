<template>
  <div class="flex items-center justify-center pt-10 space-x-8">
    <div class="relative flex px-2 pt-5 pb-4 bg-blue-900 rounded-t-3xl">
      <svg
        class="fill-current text-blue-900 absolute top-0 bottom-0 left-0 -translate-x-3/4"
        width="83"
        height="86"
        viewBox="0 0 83 86"
        fill="none"
        xmlns="http://www.w3.org/2000/svg"
      >
        <path
          d="M64.3029 8.65669C68.8626 3.17225 75.6254 0 82.7578 0H83V86H0L64.3029 8.65669Z"
        />
      </svg>
      <a href="#" v-for="bar in bars" class="flex flex-col items-center px-4 group">
        <component
          class="text-white fill-current h-7 w-7 group-hover:text-red"
          :is="bar.icon"
        />
        <span class="text-gray-600 text-xxxs mt-1.5 group-hover:text-red">
          {{ bar.title }}
        </span>
      </a>
      <svg
        class="fill-current text-blue-900 absolute top-0 bottom-0 right-0 translate-x-3/4"
        width="83"
        height="86"
        viewBox="0 0 83 86"
        fill="none"
        xmlns="http://www.w3.org/2000/svg"
      >
        <path
          d="M18.6971 8.65669C14.1374 3.17225 7.37457 0 0.242245 0H0V86H83L18.6971 8.65669Z"
        />
      </svg>
    </div>
  </div>
</template>

<script>
import Overview from "../icons/overview.svg";
import Life from "../icons/life.svg";
import Comms from "../icons/comms.svg";
import Prop from "../icons/prop.svg";
import Mech from "../icons/mech.svg";
import Power from "../icons/power.svg";
import Avionics from "../icons/avionics.svg";
import GNC from "../icons/gnc.svg";
import Thermal from "../icons/thermal.svg";
const bars = [
  { title: "Overview", icon: "Overview" },
  { title: "Life", icon: "Life" },
  { title: "Comms", icon: "Comms" },
  { title: "Prop", icon: "Prop" },
  { title: "Mech", icon: "Mech" },
  { title: "Power", icon: "Power" },
  { title: "Avionics", icon: "Avionics" },
  { title: "GNC", icon: "GNC" },
  { title: "Thermal", icon: "Thermal" },
];
export default {
  components: {
    Overview,
    Life,
    Comms,
    Prop,
    Mech,
    Power,
    Avionics,
    GNC,
    Thermal,
  },
  setup() {
    return {
      bars,
    };
  },
};
</script>
