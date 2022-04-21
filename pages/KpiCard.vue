<template>
  <div
    class="relative transform overflow-hidden rounded bg-cover bg-center shadow-md hover:scale-105"
    style="
      background-image: url('https://4kwallpapers.com/images/walls/thumbs_3t/4030.jpg');
    "
  >
    <div
      :class="bgColor"
      class="border-0 bg-opacity-10 p-2 pl-4 text-center shadow"
      style="opacity: 0.85"
    >
      <div class="text-left text-base text-black antialiased">
        {{ title }}
      </div>

      <div
        class="rounded-bottom mt-1 text-left text-2xl font-medium text-black"
      >
        <span v-if="money" class="text-black">₹</span>
        Val
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "KpiCard",
  props: {
    title: { type: String, default: "--", required: false },
    data: { default: 0, required: false },
    bgColor: {
      default: "bg-gradient-to-r from-gray-200 to-gray-400",
      required: false,
    },
    money: { type: Boolean, default: false },
  },
  computed: {
    titleStyle() {
      return {
        "font-size": "1.0rem",
        "font-weight": "500",
      };
    },
  },
};
</script>
