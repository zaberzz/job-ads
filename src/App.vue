<template>
  <div class="app"><JobList :jobs="jobs" /></div>
</template>

<script lang="ts">
import { defineComponent, ref } from "vue";
import JobList from "./components/JobList.vue";
import Job from "./types/jobs";

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
    return { jobs };
  },
});
</script>

<style></style>
