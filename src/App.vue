<template>
  <div
    id="app"
    style="font-family: 'Inter', sans-serif !important;"
    class="select-none bg-gray-300 w-screen h-screen relative flex flex-col"
  >
    <div
      class="text-gray-800 w-full py-3 px-3 flex justify-between bg-gray-200"
    >
      <div v-if="!status.stopped" class="justify-start flex">
        <div class="w-2 h-2 mr-2 rounded-full bg-green-500 my-auto"></div>
        <div class="my-auto text-xs">Zen Bridge is running...</div>
      </div>
      <div v-else class="justify-start flex">
        <div class="w-2 h-2 mr-2 rounded-full bg-red-500 my-auto"></div>
        <div class="my-auto text-xs">Zen Bridge is stopped...</div>
      </div>
      <div class="text-black justify-start flex">
        <div
          @click="toggleState"
          v-if="!status.stopped"
          class="cursor-pointer hover:text-red-100 w-6 h-6 hover:bg-red-400 text-black my-auto flex rounded"
        >
          <svg class="w-4 h-4 m-auto" fill="currentColor" viewBox="0 0 20 20">
            <path
              d="M10 18a8 8 0 100-16 8 8 0 000 16zM8 7a1 1 0 00-1 1v4a1 1 0 001 1h4a1 1 0 001-1V8a1 1 0 00-1-1H8z"
              clip-rule="evenodd"
              fill-rule="evenodd"
            ></path>
          </svg>
        </div>
        <div
          @click="toggleState"
          v-else
          class="ml-1 cursor-pointer hover:text-green-100 w-6 h-6 hover:bg-green-400 text-black my-auto flex rounded"
        >
          <svg class="w-4 h-4 m-auto" fill="currentColor" viewBox="0 0 20 20">
            <path
              d="M10 18a8 8 0 100-16 8 8 0 000 16zM9.555 7.168A1 1 0 008 8v4a1 1 0 001.555.832l3-2a1 1 0 000-1.664l-3-2z"
              clip-rule="evenodd"
              fill-rule="evenodd"
            ></path>
          </svg>
        </div>
        <div
          class="ml-1 cursor-pointer hover:text-indigo-100 w-5 h-5 hover:bg-indigo-400 text-black my-auto flex rounded"
        >
          <svg class="w-4 h-4 m-auto" fill="currentColor" viewBox="0 0 20 20">
            <path
              d="M11.49 3.17c-.38-1.56-2.6-1.56-2.98 0a1.532 1.532 0 01-2.286.948c-1.372-.836-2.942.734-2.106 2.106.54.886.061 2.042-.947 2.287-1.561.379-1.561 2.6 0 2.978a1.532 1.532 0 01.947 2.287c-.836 1.372.734 2.942 2.106 2.106a1.532 1.532 0 012.287.947c.379 1.561 2.6 1.561 2.978 0a1.533 1.533 0 012.287-.947c1.372.836 2.942-.734 2.106-2.106a1.533 1.533 0 01.947-2.287c1.561-.379 1.561-2.6 0-2.978a1.532 1.532 0 01-.947-2.287c.836-1.372-.734-2.942-2.106-2.106a1.532 1.532 0 01-2.287-.947zM10 13a3 3 0 100-6 3 3 0 000 6z"
              clip-rule="evenodd"
              fill-rule="evenodd"
            ></path>
          </svg>
        </div>
      </div>
    </div>

    <div
      class="text-gray-800 w-full py-2 border-b border-gray-400 px-3 flex justify-start bg-gray-200"
    >
      <div class="my-auto text-xs opacity-50">Activity Console</div>
    </div>
    <div
      class="overflow-y-scroll text-gray-800 w-full py-2 px-3 flex justify-start flex flex-col"
    >
      <div
        v-for="(l, i) in lines"
        :key="'l' + i"
        class="select-text my-auto text-xs opacity-75 block mb-2"
      >
        {{ l }}
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      status: {
        stopped: false
      },
      lines: ["test", "test2"]
    };
  },
  methods: {
    toggleState() {
      this.status.stopped = !this.status.stopped;
    }
  }
};
</script>

<style src="./assets/styles/styles.css" lang="css"></style>
