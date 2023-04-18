<template>
  <div class="job-list">
    <p>ordered by {{ order }}</p>
    <ul>
      <li v-for="job in jobs" :key="job.id">
        <h2>{{ job.title }} in {{ job.location }}</h2>
        <div class="salary">{{ job.salary }} toman</div>
        <div class="description">
          Lorem ipsum, dolor sit amet consectetur adipisicing elit. Placeat
          maxime esse vitae beatae illum a sequi architecto, doloremque expedita
          quasi harum culpa quia obcaecati delectus. Labore a mollitia
          consequuntur laborum.
        </div>
      </li>
    </ul>
  </div>
</template>
<script lang="ts">
import { defineComponent, PropType } from "vue";
import Job from "@/types/jobs";
import orderType from "@/types/ordertype";

export default defineComponent({
  props: {
    jobs: {
      required: true,
      type: Array as PropType<Job[]>,
    },
    order: {
      required: true,
      type: String as PropType<orderType>,
    },
  },
});
</script>
<style scoped>
.job-list {
  padding: 0;
  max-width: 960px;
  margin: 40px auto;
}
.job-list ul {
  padding: 0;
}
.job-list li {
  list-style-type: none;
  background: white;
  padding: 16px;
  margin: 16px 0;
  border-radius: 4px;
}
.job-list h2 {
  margin: 0 0 10px;
  text-transform: capitalize;
}
.salary {
  display: flex;
}
.salary img {
  width: 30px;
}
.salary p {
  color: #17bf66;
  font-weight: bold;
  margin: 10px 4px;
}
</style>
