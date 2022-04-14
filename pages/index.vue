<template>
  <div>
    <!-- <router-link to="/blog">Blog</router-link> -->
    <Date v-model="date" />

    <!-- <date-picker
      v-model="date"
      range
      :disabled="false"
      placeholder="Neeraj Date Picker"
    >
      <template #icon-calendar> ICON </template>
      <template #icon-clear> CLEAR </template>
      <template v-slot:header="{ emit }">
        <div class="w-full">
          <button class="mx-btn mx-btn-text" @click="selectNextThreeDay(emit)">
            Next Three Day
          </button>
        </div>
      </template>
    </date-picker> -->
    <button @click="printTime">click</button>
  </div>
</template>

<script>
import Vue from "vue";
import Date from "./Date.vue";

export default Vue.extend({
  name: "Index",
  components: { Date },
  data() {
    return {
      myName: "",
      date: null,
    };
  },
  methods: {
    printTime() {
      console.log(this.myName);
      console.log(this.date);
    },
    neerajdis(date) {
      return date > new Date();
    },
  },
});
</script>
