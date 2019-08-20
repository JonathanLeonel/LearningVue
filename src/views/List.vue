<template>
  <div class="list">
    <h1>Lista de tareas pendientes (o por hacer)</h1>
    <input v-model="newTask" type="text" v-on:keypress="inputKeypress" />
    <button v-on:click="addTask">+</button>
    <ul id="example-1">
      <li v-for="task in tasks" v-bind:key="task.id">{{ task.text }}</li>
    </ul>
  </div>
</template>

<script>
let lastId = 0;

export default {
  name: "list",
  data: () => ({
    newTask: "",
    tasks: [{ id: 0, text: "Primera tarea", checked: false }]
  }),
  methods: {
    addTask() {
      this.tasks.push({ id: ++lastId, text: this.newTask, checked: false });
      this.newTask = "";
    },
    inputKeypress(event) {
      if (event.keyCode === 13) {
        event.preventDefault();
        this.addTask();
      }
    }
  }
};
</script>