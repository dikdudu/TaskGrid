<template>
  <dir class="tasks">
      <template>
          <div v-for="task in tasks" :key="task.name">{{task.name}}</div>
      </template>
  </dir>
</template>

<script>
export default {
    props: {
        tasks: {type: Array, require: true}
    }
}
</script>

<style>

</style>