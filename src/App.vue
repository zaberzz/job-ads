<template>
  <div class="app">
    <header>
      <div class="order">
        <button @click="handleClick('title')">order by title</button>
        <button @click="handleClick('salary')">order by salary</button>
        <button @click="handleClick('location')">order by location</button>
      </div>
    </header>

    <JobList :jobs="jobs" :order="order" />
  </div>
</template>

<script lang="ts">
import { defineComponent, ref } from "vue";
import JobList from "./components/JobList.vue";
import Job from "./types/jobs";
import orderType from "./types/ordertype";

export default defineComponent({
  name: "App",
  components: { JobList },
  setup() {
    const jobs = ref<Job[]>([
      { title: "farmer", location: "sarough", salary: 3000, id: "1" },
      { title: "fisherman", location: "anzali", salary: 3500, id: "2" },
      { title: "plumber", location: "natanz", salary: 2000, id: "3" },
      { title: "prison guard", location: "karaj", salary: 4500, id: "4" },
    ]);
    const order = ref<orderType>("title");
    const handleClick = (term: orderType) => {
      order.value = term;
    };
    return { jobs, handleClick, order };
  },
});
</script>

<style>
header {
  text-align: center;
}
header .order {
  margin-top: 20px;
}
button {
  margin: 0 10px;
  color: #1195c9;
  border: 3px solid #1195c9;
  background: #d5f0ff;
  padding: 8px 16px;
  border-radius: 4px;
  cursor: pointer;
  font-weight: bold;
}
</style>
