<template>
  <div>
    <!-- <router-link to="/">Home</router-link> -->

    <h1>Welcome to blog</h1>
    <input
      type="text"
      v-model="enteredText"
      class="border-2 border-indigo-600"
    />
  </div>
</template>

<script>
import Vue from "vue";

export default Vue.extend({
  name: "Blog",
  computed: {
    enteredText: {
      get() {
        return this.value;
      },
      set(val) {
        this.$emit("input", val);
      },
    },
  },
});
</script>

<style></style>
