<template>
  <div id="app" class="container">
    <h1>Crea una nueva tarea</h1>
    <section>
      <label for="task">Tarea</label>
      <input
        id="task"
        type="text"
        v-model="task"
        placeholder="ingrese nueva tarea"
      />
      <button @click="addTask">Crear</button>
    </section>
    <section class="center">
      <h2>Lista</h2>
      <ol>
        <li v-for="(task_iteracion, i) in tasks" :key="i">
          {{ task_iteracion }}
        </li>
      </ol>
    </section>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      task: "",
      tasks: [],
    };
  },
  methods: {
    addTask() {
      const { task } = this;
      this.tasks.push(task);
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.container {
  width: 100%;
  padding: 2rem 2rem;
  margin: 2rem 2rem;
}

label {
  font-weight: 700;
  margin: 0rem 1rem;
}

button {
  padding: 0.1rem 0.75rem;
  margin: 0rem 1rem;
}

.center {
  display: flex;
  flex-direction: column;
  align-items: center;
}
</style>
