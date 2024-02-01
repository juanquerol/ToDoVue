<template>
  <div id="app">
    <h1>To Do List</h1>
    <div class="center-container">
      <TaskList />
    </div>
  </div>
</template>

<script>
import TaskList from './components/TaskList.vue';

export default {
  name: 'App',
  components: {
    TaskList
  }
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
  height: 100vh; /* Asegura que el contenedor ocupa el 100% de la altura de la pantalla */
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

.center-container {
  width: 100%; /* Asegura que el contenedor ocupa el 100% del ancho disponible */
}
</style>