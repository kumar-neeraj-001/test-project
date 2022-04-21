<template>
  <div class="grid grid-cols-2">
    <ul v-if="!loading">
      <li v-for="{ title, id } in partOfArr" :key="id">
        {{ id }} -> {{ title }}
      </li>
    </ul>
    <ul v-if="!loading">
      <li
        class="inline-block m-2 cursor-pointer"
        v-for="index in length"
        :key="index"
      >
        <button class="active:bg-purple-300">
          <strong @click="pagination(index)">{{ index }}</strong>
        </button>
      </li>
      <div class="mt-5">
        <strong @click="viewCount = 5" class="font-semibold m-2">5</strong>
        <strong @click="viewCount = 10" class="font-semibold m-2">10</strong>
        <strong @click="viewCount = 20" class="font-semibold m-2">20</strong>
        <strong @click="viewCount = 50" class="font-semibold m-2">50</strong>
        <strong @click="viewCount = 1 / 0" class="font-semibold m-2"
          >All</strong
        >
      </div>
    </ul>
  </div>
</template>

<script>
import axios from "axios";

export default {
  data() {
    return {
      items: [],
      partOfArr: [],
      loading: false,
      lenght: 0,
      viewCount: 10,
    };
  },
  beforeMount() {
    this.getData();
  },
  watch: {
    viewCount() {
      this.loading = true;
      this.length = this.items.length / this.viewCount;
      this.pagination(1);
      this.loading = false;
    },
  },
  methods: {
    async getData() {
      this.loading = true;
      this.items = await axios.get(
        "https://jsonplaceholder.typicode.com/todos"
      );
      this.items = this.items.data;
      this.length = this.items.length / this.viewCount;
      this.pagination(1);
      this.loading = false;
    },
    pagination(val) {
      val--;
      this.partOfArr = this.items.slice(
        val * this.viewCount,
        (1 + val) * this.viewCount
      );
    },
  },
};
</script>

<style></style>
