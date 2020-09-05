<template>
  <div>
    <h1 id="titulo">Agrega tu tarea...</h1>
    <input v-model="tarea" @keyup.enter="agregarTarea" type="text" />
    <button id="add" @click="agregarTarea">
      <b>+</b>
    </button>
    <h2 v-show="tareas.length != 0">Listado de tareas</h2>
    <tarea v-for="(tarea,i) in tareas" :key="i" :tarea="tarea" :indice="i" @borrar="eliminarTarea"></tarea>
  </div>
</template>

<script>
import Tarea from "./components/Tarea";
export default {
  components: {
    Tarea,
  },
  data() {
    return {
      name: "To do list",
      tarea: "",
      tareas: [],
    };
  },
  methods: {
    agregarTarea() {
      if(!this.tarea == ''){
        this.tareas.push(this.tarea.toUpperCase());
      this.tarea = "";

      }else{alert('Ingresa una tarea a tu lista')}
      
    },
    eliminarTarea(indice) {
      this.tareas.splice(indice,1)

    }
  },
};
</script>

<style>
body {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  background-color: indianred;
  color: white;
  display: flex;
  justify-content: center;
  font-family: "Comic Neue", cursive;
}
#titulo {
  font-family: "Chelsea Market", cursive;
}
input {
  width: 250px;
  margin: 0 15px 0 0;
  border: 1px solid brown;
  border-radius: 3px;
}
button {
  width: 30px;
  height: 30px;
  border-radius: 50%;
}
#add {
  background-color: lightgreen;
  color: green;
  font-size: 22px;
  border: 1px solid green;
}
#subtract {
  width: 30px;
  height: 30px;
  margin: 5px;
  background-color: pink;
  color: red;
  font-size: 18px;
  border: 1px solid red;
}
</style>

