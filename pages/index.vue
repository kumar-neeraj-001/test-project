<template>
  <div>
    <!-- <Card /> -->
    <!-- <input type="text" v-model="name" /> -->
    <!-- <MyInput v-model="name" /> -->
    <hr />
    <hr />
    <hr />
    <!-- <Pagination /> -->
    <KpiCard />
  </div>
</template>

<script>
import Vue from "vue";
import Card from "./Card.vue";
import MyInput from "./MyInput.vue";
import Pagination from "./Pagination.vue";
import KpiCard from "./KpiCard.vue";

export default Vue.extend({
  name: "Index",
  components: { Card, MyInput, Pagination, KpiCard },
  data() {
    return {
      name: "",
    };
  },
});
</script>
