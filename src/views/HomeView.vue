<template>
  <div class="app">
    <header>
      <div class="order">
        <button @click="handleClick('title')">Order by title</button>
        <button @click="handleClick('salary')">Order by salary</button>
        <button @click="handleClick('location')">Order by location</button>
      </div>
    </header>

    <JobsList :jobs="jobs" :order="order" />
  </div>
</template>

<script lang="ts">
import { defineComponent, ref } from 'vue'
import JobsList from '../components/JobsList.vue'
import Job from '../types/job'
import OrderTerm from '@/types/OrderTerm'

export default defineComponent({
  name: 'HomeView',
  components: { JobsList },
  setup () {
    // const state = reactive({
    //   name: 'Barry',
    //   age: 25 as string | number
    // })
    // const aaa = toRefs(state)
    // console.log(aaa)
    // // return { ...toRefs(state) }
    // const name = ref('Link')
    // const age = ref<number | string>(25)
    // return { name, age }

    // 上面是練習語法

    const jobs = ref<Job[]>([
      { title: 'farmer', location: 'london', salary: 5000, id: '1' },
      { title: 'police', location: 'USA', salary: 4100, id: '2' },
      { title: 'teacher', location: 'brndon', salary: 3000, id: '3' },
      { title: 'nurse', location: 'ddndon', salary: 3500, id: '4' },
      { title: 'house', location: 'oaaon', salary: 5400, id: '5' }
    ])

    const order = ref<OrderTerm>('title')

    const handleClick = (term: OrderTerm) => {
      order.value = term
    }

    return { jobs, handleClick, order }
  }
})
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
