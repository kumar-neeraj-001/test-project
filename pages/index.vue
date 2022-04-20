<template>
  <div>
    <Card />
  </div>
</template>

<script>
import Vue from "vue";
import Card from "./Card.vue";

export default Vue.extend({
  name: "Index",
  components: { Card },
});
</script>
