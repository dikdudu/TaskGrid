<template>
  <div id="app">
    <h1>Tarefas</h1>
    <NewTask @taskAdded="addTask" />
    <TaskGrid :tasks="tasks" />
  </div>
</template>

<script>
import NewTask from "./components/NewTask.vue";
import TaskGrid from "./components/TaskGrid.vue";

export default {
  components: { TaskGrid, NewTask },
  data() {
    return {
      tasks: [
        { name: "Lavar Loudsd", pending: false },
        { name: "Comprar Roupas", pending: true },
      ],
    };
  },
  methods: {
    addTask(task) {
      const sameName = t => t.name === task.name
      const reallyName = this.tasks.filter(sameName).length == 0
      if(reallyName){
        this.tasks.push({
          name: task.name,
          pending: true,
        })
      }
    },
  },
};
</script>

<style>
body {
  font-family: "Lato", sans-serif;
  background: linear-gradient(to right, rgb(22, 34, 42), rgb(58, 96, 115));
  color: #fff;
}

#app {
  display: flex;
  flex: 1;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  height: 100vh;
}

#app h1 {
  margin-bottom: 5px;
  font-weight: 300;
  font-size: 3rem;
}
</style>
