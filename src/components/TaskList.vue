<template>
    <div class="contenedor">
      <div class="card" v-for="datos in tasks" :key="datos.id" @click="toggleDone(datos)" >
        <h3>{{ datos.text }}</h3>
        <h2 v-if="datos.done"> ✅</h2>
        <h4 v-else>❌</h4>
        <button @click="eliminarTarea(datos)" class="eliminar">Eliminar</button>
      </div>
  
      <!-- Agrega un nuevo campo de entrada y un botón -->
      <div class="add-task">
        <input v-model="newTaskText" placeholder="Nueva tarea">
        <button @click="agregarTarea" class="agregar">Agregar tarea</button>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        tasks: [
          { id: 1, text: 'Hacer la compra', done: false },
          { id: 2, text: 'Estudiar Vue.js', done: false },
          
          // Agrega más tareas según sea necesario
        ],
        newTaskText: '', // Nuevo campo de entrada para la nueva tarea
      };
    },
    methods: {
      toggleDone(task) {
        // Cambia el valor de 'done' al hacer clic en la tarjeta
        task.done = !task.done;
      },
      agregarTarea() {
        // Añade una nueva tarea al array de tareas
        if (this.newTaskText.trim() !== '') {
          const nuevaTarea = {
            id: this.tasks.length + 1,
            text: this.newTaskText,
            done: false,
          };
          this.tasks.push(nuevaTarea);
          this.newTaskText = ''; // Limpia el campo después de agregar la tarea
        }
      },
      eliminarTarea(task) {
      // Filtra las tareas para mantener solo las que no coinciden con la tarea a eliminar
      this.tasks = this.tasks.filter((t) => t !== task);
    },
    },
  };
  </script>
  
  <style>
  .card {
    height: 5rem;
    width: 20rem;
    border-radius: 10px;
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    align-items: center;
    border: #222 1px solid;
    cursor: pointer;
    margin-top: 10px;
  }
  
  .card:hover {
    background-color: aliceblue;
  }
  
  .add-task {
    margin-top: 20px;
  }
  
  .add-task input {
    padding: 8px;
    margin-right: 8px;
    border-radius: 10px;
  }
  
  .add-task button {
    padding: 8px;
    
    background-color: rgb(138, 238, 238);
  }
  button{
    border-radius: 10px;
  }
  .agregar:hover{
    background-color: rgb(124, 224, 224);
    
  }
  .eliminar{
    
    background-color: rgb(255, 141, 141);
  }
  .eliminar:hover{
    background-color: rgb(177, 122, 122);
  }
  </style>
  