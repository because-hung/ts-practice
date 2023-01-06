<template>
  <div class="job-list">
    <p>Ordered by {{ order }}</p>
    <ul>
      <li v-for="job in jobs" :key="job.id">
        <h2>{{ job.title }} in {{ job.location }}</h2>
        <div class="salary">
          <p>{{ job.salary }} NT dollars</p>
        </div>
        <div class="desc">
          Lorem, ipsum dolor sit amet consectetur adipisicing elit. Repellat excepturi sed aut eum recusandae quaerat. Deserunt illum quod beatae quam earum, numquam perspiciatis amet ducimus incidunt illo ea officiis nemo omnis ad recusandae impedit soluta ullam unde. Porro illum ut culpa eius sed non accusantium soluta, error ullam, dicta veniam.
        </div>
      </li>
    </ul>
  </div>
</template>
<script lang="ts">
import Job from '@/types/job'
import OrderTerm from '@/types/OrderTerm'
import { defineComponent, PropType } from 'vue'

export default defineComponent({
  props: {
    jobs: {
      required: true,
      type: Array as PropType<Job[]>
    },
    order: {
      required: true,
      type: String as PropType<OrderTerm>
    }
  }
})
</script>

<style scoped>
  .job-list {
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
