<template>
  <div class="tasks-grid">
      <template>
          <Task v-for="tsk in tasks" :key="tsk.name" 
            :task="tsk"></Task>
      </template>
  </div>
</template>

<script>
import Task from "./Task.vue"
export default {
    components: {Task},
    props: {
        tasks: {type: Array, require: true}
    }
}
</script>

<style>

</style>