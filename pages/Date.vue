<template>
  <div>
    <date-picker style="width: 225px" v-model="dateRange" range>
      <template #icon-calendar> ICON </template>
      <template #icon-clear> CLEAR </template>
      <template v-slot:header="{ emit }">
        <div>
          <button class="mx-btn mx-btn-text" @click="today(emit)">Today</button>
          <button class="mx-btn mx-btn-text" @click="yesterday(emit)">
            Yesterday
          </button>
          <button class="mx-btn mx-btn-text" @click="thisMonth(emit)">
            This Month
          </button>
          <button class="mx-btn mx-btn-text" @click="lastMonth(emit)">
            Last Month
          </button>
          <button class="mx-btn mx-btn-text" @click="thisYear(emit)">
            This Year
          </button>
        </div>
      </template>
    </date-picker>
  </div>
</template>

<script>
import DatePicker from "vue2-datepicker";
import moment from "moment";

export default {
  name: "Date",
  components: { DatePicker },
  props: {
    value: { required: true },
  },
  computed: {
    dateRange: {
      get() {
        return this.value;
      },
      set(val) {
        console.log(val);
        this.$emit("input", val);
      },
    },
  },
  mounted() {
    this.dateRange = this.value;
  },
  methods: {
    today(emit) {
      const start = new Date();
      const date = [start, start];
      emit(date);
    },
    yesterday(emit) {
      const start = new Date(moment().subtract(1, "day"));
      const date = [start, start];
      emit(date);
    },
    thisMonth(emit) {
      const start = new Date(moment().startOf("month"));
      const end = new Date(moment().endOf("month"));
      const date = [start, end];
      emit(date);
    },
    lastMonth(emit) {
      const start = new Date(moment().startOf("month").subtract(1, "month"));
      const end = new Date(moment().endOf("month").subtract(1, "month"));
      const date = [start, end];
      emit(date);
    },
    thisYear(emit) {
      const start = new Date(moment().startOf("year"));
      const end = new Date(moment().endOf("year"));
      const date = [start, end];
      emit(date);
    },
  },
};
</script>

<style></style>
