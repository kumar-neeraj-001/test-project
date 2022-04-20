<template>
  <div>
    <div
      class="max-w-sm rounded-xl overflow-hidden shadow hover:shadow-lg"
      :class="changeColor"
    >
      <div class="px-6 py-4">
        <div class="font-bold text-xl mb-2">The Coldest Sunset</div>
        <p class="text-gray-700 text-base">
          Lorem ipsum dolor sit amet, consectetur adipisicing elit. Voluptatibus
          quia, nulla! Maiores et perferendis eaque, exercitationem praesentium
          nihil.
        </p>
      </div>
      <div class="px-6 pt-4 pb-2">
        <span
          class="inline-block bg-gray-200 rounded-full px-3 py-1 text-sm font-semibold text-gray-700 mr-2 mb-2"
          >#photography</span
        >
        <span
          class="inline-block bg-gray-200 rounded-full px-3 py-1 text-sm font-semibold text-gray-700 mr-2 mb-2"
          >#travel</span
        >
        <span
          class="inline-block bg-gray-200 rounded-full px-3 py-1 text-sm font-semibold text-gray-700 mr-2 mb-2"
          >#winter</span
        >
      </div>
    </div>
    <h1>Five</h1>
    <ul>
      <li v-for="{ item, index } in ['cd', 'cnds', 'ckjndsk']" :key="index">
        {{ item }}
      </li>
    </ul>
    <h1 class="text-2xl">
      {{ windowWidth }}
    </h1>
    <h1>Fourth</h1>
  </div>
</template>

<script>
export default {
  name: "Card",
  data() {
    return {
      windowWidth: window.innerWidth,
    };
  },

  mounted() {
    this.$nextTick(() => {
      window.addEventListener("resize", this.onResize);
    });
  },

  computed: {
    changeColor() {
      if (this.windowWidth > 600) {
        return "bg-green-400";
      }
      return "bg-yellow-400";
    },
  },

  methods: {
    onResize() {
      this.windowWidth = window.innerWidth;
    },
  },
};
</script>
