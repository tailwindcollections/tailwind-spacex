<template>
  <div
    class="w-full min-h-screen px-12 pt-10 font-sans bg-cover border-blue-900 border-b-16"
    style="background-image: url('/img/background.png')"
  >
    <div
      class="absolute inset-0 pointer-events-none bg-gradient-to-b from-black/30 to-transparent"
    />
    <h1 class="relative text-2xl text-white font-semibold text-center uppercase">
      Vehicle overview
    </h1>
    <div class="flex items-start mt-4">
      <LeftPane />

      <div class="flex w-full flex-col px-16 pt-6 relative">
        <TopStats />

        <BottomStats />

        <Connections />

        <div
          class="absolute flex flex-col justify-center -translate-x-1/2 left-1/2 top-52"
        >
          <img class="w-[380px] h-auto" src="/img/Space-X-Dragon.png" alt="" />
        </div>
        <div class="relative flex self-center pt-24">
          <span class="text-white uppercase text-xxxs">Cabin Mics :</span>
          <span class="uppercase text-red text-xs">Recording</span>
        </div>
      </div>

      <RightPane />
    </div>

    <div class="flex justify-between">
      <div class="flex items-center w-80">
        <button
          class="relative z-10 px-8 py-6 text-sm font-bold uppercase bg-white rounded"
        >
          System
        </button>
        <button
          class="relative -translate-x-1 px-8 py-4 border rounded text-white text-sm font-bold border-gray-600/50 bg-opacity-[0.1] uppercase"
        >
          Cabin
        </button>
      </div>

      <Dock />

      <div class="flex items-center justify-end space-x-5 w-80">
        <span class="tracking-wider text-gray-600 text-xxs whitespace-nowrap">
          Power, Engine, Comms
        </span>
        <button
          class="px-8 py-4 border rounded text-white text-sm font-bold border-gray-600/50 bg-gray-900 bg-opacity-[0.1] uppercase"
        >
          More
        </button>
      </div>
    </div>
  </div>
</template>

<script>
import Dock from "./components/Dock.vue";
import Connections from "./components/Connections.vue";
import BottomStats from "./components/BottomStats.vue";
import TopStats from "./components/TopStats.vue";
import RightPane from "./components/RightPane.vue";
import LeftPane from "./components/LeftPane.vue";
export default {
  components: { LeftPane, RightPane, TopStats, BottomStats, Connections, Dock },
};
</script>
