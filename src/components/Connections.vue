<template>
  <div class="w-40 mt-8 ml-16">
    <div class="py-3 text-gray-600 uppercase border-b border-gray-600 text-xs">
      Connections
    </div>
    <div class="pt-2 space-y-3">
      <div v-for="connection in connections" class="flex justify-between text-xxxs">
        <span class="text-gray-600"> {{ connection.name }} </span>
        <span class="font-bold text-white capitalize"> {{ connection.status }} </span>
      </div>
    </div>
  </div>
</template>

<script>
const connections = [
  { name: "Manual Rigs", status: "connected" },
  { name: "Changelog", status: "connected" },
  { name: "Airlock", status: "connected" },
  { name: "Wing", status: "connected" },
];
export default {
  setup() {
    return {
      connections,
    };
  },
};
</script>
