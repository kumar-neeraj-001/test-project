<template>
  <div>
    <div
      class="max-w-sm rounded-xl overflow-hidden shadow hover:shadow-lg"
      :class="changeColor"
    >
      <div class="px-6 py-4">
        <div class="font-bold text-xl mb-2">Title aayega ider</div>
        <p class="text-gray-700 text-base">
          Lorem ipsum dolor salary increase kr do sit amet, consectetur
          adipisicing elit. Voluptatibus quia, nulla! Maiores et perferendis
          eaque, exercitationem praesentium nihil.
        </p>
      </div>
      <div class="px-6 pt-4 pb-2">
        <span
          class="inline-block bg-gray-200 rounded-full px-3 py-1 text-sm font-semibold text-gray-700 mr-2 mb-2"
          >Sucess</span
        >
        <span
          class="inline-block bg-gray-200 rounded-full px-3 py-1 text-sm font-semibold text-gray-700 mr-2 mb-2"
          >Warning</span
        >
        <span
          class="inline-block bg-gray-200 rounded-full px-3 py-1 text-sm font-semibold text-gray-700 mr-2 mb-2"
          >Kuch bhi</span
        >
      </div>
    </div>
    <h1 class="text-2xl">Window Width - {{ windowWidth }}</h1>
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
      if (this.windowWidth > 800) {
        return "bg-purple-400";
      }
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
